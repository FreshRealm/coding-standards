# References

## References & Useful Tutorials/Documentation
- [Javascript Documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference)
- [Node.js guides](https://nodejs.org/en/docs/guides/)
- [Current LTS Node.js Documentation](https://nodejs.org/dist/latest-v8.x/docs/api/)
- [Express Web Framework](https://expressjs.com/)
- [Angular.js Style Guide](https://github.com/johnpapa/angular-styleguide/blob/master/a1/README.md)
- [Current Angular.js Developer Guide](https://docs.angularjs.org/guide)
- [Current Angular.js API Documentation](https://docs.angularjs.org/api)
- [Visual Studio Code cross-platform text editor](https://code.visualstudio.com/)
- [FR Webpack Angular Atom Snippets](https://atom.io/packages/angularjs-styleguide-webpack-snippets)
- [Pivotal Web Services (Cloud Foundry) Documentation](http://docs.run.pivotal.io/starting/index.html)
- [FreshRealm Merchant API Documentation](https://freshrealm.docs.apiary.io/)
- [FreshRealm Merchant API v3 Documentation](https://freshrealmv3.docs.apiary.io/)
- [Git Actions Visualizer](https://onlywei.github.io/explain-git-with-d3/)
- [Spectacles Window Management App for macOS](https://www.spectacleapp.com/)
- [Papertrail Setup for Cloud Foundry Apps](https://help.papertrailapp.com/kb/hosting-services/cloud-foundry/)

## Useful Git Tools
WIP/UnWIP aliases: add the following to your `~/.gitconfig` file.
```
[alias]
    wip = !git add -N . && git commit -am WIP
    unwip = !git log -1 --oneline | grep WIP > /dev/null && git reset --soft @^ && git reset .
```

Install https://github.com/pivotal/git_scripts and then add a `~/.pairs` file in the following format. Note, if you are using SourceTree, be sure to turn off the “Allow SourceTree to modify your global Mercurial and Git configuration files” setting.
```
# .pairs - configuration for 'git pair'
pairs:
  # <initials>: <Firstname> <Lastname>[; <email-id>]
  jg: John Grogg; johng
  ew: Ersun Warncke; ersun
  sa: Sakwa Alvitre; sakwa
  oo: Ondrej Nebesky; ondrej
  dj: Daniel Johansson; daniel.johansson
  st: Samuel Thompson; samuel.thompson
  cn: Cinish Narayanan; cinish
  kh: Kyle Hoberg; kyle.hoberg
  sd: Sam Decanio; sam.decanio
  mk: Michael Kaiser; michael.kaiser
email:
  prefix: pair
  domain: freshrealm.co
  no_solo_prefix: true
global: true  # Set to true for git-pair to change git configuration for all your projects
```

## Useful Visual Studio Code Packages and Settings
- [Angular 4 and TypeScript/HTML VS Code Snippets - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=danwahlin.angular2-snippets)
- [Git Lens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
- [Partial Diff](https://marketplace.visualstudio.com/items?itemName=ryu1kn.partial-diff)
- [TSLint](https://marketplace.visualstudio.com/items?itemName=eg2.tslint)
- [Beautify](https://marketplace.visualstudio.com/items?itemName=HookyQR.beautify)
- [EditorConfig](https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig)
- [Path Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense)
- [Project Manager](https://marketplace.visualstudio.com/items?itemName=alefragnani.project-manager)