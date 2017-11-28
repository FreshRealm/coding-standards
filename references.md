# References

## References & Useful Tutorials/Documentation
Javascript Documentation
Node.js guides
Current LTS Node.js Documentation
Express Web Framework
Angular Style Guide
Current Angular.js Developer Guide
Current Angular.js API Documentation
Atom cross-platform text editor
FR Webpack Angular Atom Snippets
Webpack Frontend Build System
Less CSS Pre-processor
JSHint linter
Pivotal Web Services (Cloud Foundry) Documentation
FreshRealm Merchant API Documentation
Git Actions Visualizer
Spectacles Window Management App for macOS
Papertrail Setup for Cloud Foundry Apps

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

## Useful Atom Packages and Settings
FR Webpack Angular Atom Snippets
Linter & https://atom.io/packages/linter-jshint - shows in-line linting status
https://atom.io/packages/fixmyjs - automatically fixes simple linting errors (respects the .jshintrc file) (to finish installing: As mentioned by @sindresorhus in #7, npm install in ~/.atom/packages/fixmyjs works)
https://atom.io/packages/atom-beautify
Atom-chai-snippets
File-icons
Project-manager
Useful Atom Snippets

