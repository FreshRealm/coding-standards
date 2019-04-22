# References

## References & Useful Tutorials/Documentation
- [Javascript Documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference)
- [Node.js guides](https://nodejs.org/en/docs/guides/)
- [Current LTS Node.js Documentation](https://nodejs.org/dist/latest-v8.x/docs/api/)
- [Express Web Framework](https://expressjs.com/)
- [Angular.js Style Guide](https://github.com/johnpapa/angular-styleguide/blob/master/a1/README.md)
- [Visual Studio Code cross-platform text editor](https://code.visualstudio.com/)
- [Pivotal Web Services (Cloud Foundry) Documentation](http://docs.run.pivotal.io/starting/index.html)
- [Git Actions Visualizer](https://onlywei.github.io/explain-git-with-d3/)
- [Spectacles Window Management App for macOS](https://www.spectacleapp.com/)

## Useful Git Tools
WIP/UnWIP aliases: add the following to your `~/.gitconfig` file.
```
[alias]
    wip = !git add -N . && git commit -am WIP
    unwip = !git log -1 --oneline | grep WIP > /dev/null && git reset --soft @^ && git reset .
```

## Useful Visual Studio Code Packages and Settings
- [Angular 4 and TypeScript/HTML VS Code Snippets - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=danwahlin.angular2-snippets)
- [Git Lens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
- [TSLint](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-typescript-tslint-plugin)
- [Beautify](https://marketplace.visualstudio.com/items?itemName=HookyQR.beautify)
- [EditorConfig](https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig)
- [Debugger for Chrome](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome)