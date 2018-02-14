# General Guidelines
Here are some general guidelines that should be followed in all projects.

## When in Doubt, Ask!
Things move quickly and change often at FreshRealm. This means that at times requests and requirements can become confusing. When this happens, don’t hesitate to ask the PM/Senior Engineering for clarification.

We as an engineering team also strive to use the best technologies for the problem at hand. This means that sometimes you will need to learn a new framework, a new architecture pattern, or even a new language. When this happens use your fellow engineers and the Senior Engineering team to their fullest. Questions are encouraged and collaboration is valued.

## Pair Programming
The engineering team will program in pairs if necessary. Pair programming increases quality and reduce bugs, as well as to naturally spread knowledge of the systems and tools through collaboration.

Any time an engineer solos on a task they must have their code reviewed via a Pull Request by at least one other engineer. Pairs can also ask for Code Review if they want additional feedback before merging their work (this can be especially helpful on complex tasks).

## Test Driven Development
All software projects should follow Test Driven Development practices. In short: unit tests should be written before code; all business logic should be covered by unit tests; only the code under test should be tested (use mocks and stubs!).

For Services and other classes, all methods should have unit tests. If method A calls method B, then method A’s unit tests should stub method B’s behavior.

A useful pattern for Service classes in particular is to have a main method that strings together other class methods, passing data between them. This allows for easy testing of the high-level business logic of the service as well as the low level logic of the other methods.

No http or database calls should ever actually run in unit tests. For code that uses http or database requests (perhaps for API calls), if at all possible the request module/library should be stubbed. If stubbing is not possible for some reason, then an http request mocking library (like nock in javascript apps) should be used.

## Continuos Integration
All Pivotal Cloud Foundry Angular.io and Node 8+ applications are tested and deployed automaticaly using Circle CI, so developers don't have to. Once pull request is complete and pushed to the `master` branch, Circle CI will test the code and deploy to test space in a couple of minutes. Any commit to release/* branch gets deployed to staging space. Please subscribe to your projects on [Circle CI](https://circleci.com/bb/freshrealm) page to receive notifications about failing builds.

## Business Logic Belongs in Services
Business logic should be implemented in dedicated Services. When possible the Service should be given raw data to manipulate and return raw data, allowing the Controller or other calling context to deal with using Data Models for finding input data and saving output data. This allows for easy testing of the business logic and simple re-use of the business logic.

## Data Models are for Persistence
Data Models should only deal with data validation and persistence. This allows them to essentially need no testing (since they are just using the features of an ORM or other data management framework) and improves their mock-ability.

## Controllers are Plumbing
Controllers should simply act as plumbing, connecting external requests to Data Models and Services. They should only ever have the bare minimum of business logic within them (if it is more than a few lines of logic it should be moved into a Service). 

When possible, RESTful controllers should be used in lieu of dedicated controller actions. This means adding filtering to list actions and having update actions that can be used by various contexts as needed.

## Don’t Over Engineer or Pre-optimize
It’s often tempting to add complexity to a feature in an attempt to not need to revisit it in the future. This should be avoided as much as possible so that the systems remains as simple as possible. Added complexity should wait until it is actually needed. Examples of over engineering include: adding functionality that has not yet been requested by the business, making a business logic algorithm more complex in an attempt to make it more efficient when the added efficiency is not yet needed, creating a parent class and child class when no other child classes are planned/needed at the moment.

Note, this does not mean you cannot optimize your code or add complexity that is of value. The key is to know the cost of the complexity you are adding and ask yourself if said complexity is really needed right now. When in doubt, talk with the Senior Engineering team for guidance.

## Deployment Actions
Often times a story will require server configuration or other actions before the story can be fully functional. Examples of this may be that a script needs to be run on the server, a local server configuration will need to be updated, production data will need to be updated, and so on. In these instances, it is important to tag the appropriate story with the `needs deployment action` label so that an engineer and/or QA person deploying software can see which stories require additional work at a quick glance.

When a story requires additional action, it is also important to update the story’s description as well. If something needs to be completed before the deployment can be completed, use the Pre Deployment Action header within the story’s description and include a brief summary of what needs to be done before deployment can happen. Conversely, if something needs to be done after a deployment, use the Post Deployment Action header and specify the necessary actions.