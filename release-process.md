# Release Process

## Continuous Delivery
``` 
Continuous Delivery is the ability to get changes of all types—including new features, configuration changes, bug fixes and experiments—into production, or into the hands of users, safely and quickly in a sustainable way.

We achieve all this by ensuring our code is always in a deployable state, even in the face of developers making changes on a daily basis. We thus completely eliminate the integration, testing and hardening phases that traditionally followed “dev complete”, as well as code freezes. 
```
[Reference](https://continuousdelivery.com/)

This is our goal when releasing software, however, we deal with real time operations of a business and sometimes need to schedule our releases to not be disruptive. 

When permitted, all software should be released as soon as possible.

## Initial Release (Very first deployment per space)
The initial release of an application has some added complexity when hosted on PWS and must be done by a developer. The application needs the user provided services to be created, the database provisioned, and the application manually pushed using cf push.

### Example
```
cf login -a api.run.pivotal.io
#CF Environment Configuration
cf cups myapp-user-provided-service -p '{"jsonParams":"some-service-params"}'
#CF Deployment
yarn install && yarn build && cf t -s test && cf push myapp -d cf-test.myfrcloud.com -b default
```

## Immediate Releases
Subsequent releases should follow the process below, given that scripts are written for deploying with zero downtime (cf v3-zdt-push), and it is hooked into CircleCI waiting for the master branch commits for test space deployments, and the "v#.#.#" tag to trigger production deployments.

When preparing a standard (immediate) release, do the following steps:

- **Verify that the tests have passed in CircleCI, and the application runs as expected in the test space.**
- Bump the version number within the release commit, commit this file change to the repo.
    - This can be done as a part of the story you are committing instead of an additional commit.
    - Bump the major version for breaking changes
    - Bump the minor version for new features
    - Bump the hotfix version for bug fixes
- Perform all pre-deployment tasks.
- Deploy the release branch to the production environment by assigning a tag in the format of "v{major}.{minor}.{patch}"
- Perform all post-deployment tasks.
- **Verify that the tests have passed in CircleCI, and the application runs as expected in the production space.**
- Move the story to Done in Jira!

For hotfix releases, the same general process should be followed, except the branch name should be in the format of “hotfix/v{major}.{minor}.{patch}” (as stated above in the Git Branch Management section).

## Scheduled Releases
- Document all pre and post deployment actions clearly in the story, if any steps are necessary.
- If not self-evident as to why this story needs a scheduled release, add a comment to the story in Jira as to why this needs to be scheduled.
- As a developer, you are done at this point.
- As the person performing the deployment
    - Communicate with the team responsible for release notes or SOPs to update documentation.
    - Communicate with plant staff or other affected parties to choose a time to deploy, then follow the above release process. 
    - Involve the developer if anything unexpected occurs.