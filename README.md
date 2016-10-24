# Electron App

Sample project to reproduce [this Electron issue](https://github.com/electron/electron/issues/7603): "_openExternal url crash on macOS Sierra_"


## Steps

I've just edited electron/main.js file adding thoose lines
```
mainWindow.webContents.on('new-window', function(e, url) {
    e.preventDefault();
    electron.shell.openExternal(url);
});
```

Then in www/index.html

```
<h4>
    This is a <a href="https://google.com" target="_blank">Link</a>
</h4>
```

When running in electron, clicking on "Link" will cause a crash of the app after a few seconds.


## Installation

    `npm install` or `yarn`

This command will setup node_modules for running or testing application.


## Usage

    `npm start` or `yarn start`

Runs electron app

    `npm build` or `yarn build`

Builds electron app
