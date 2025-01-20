# desktop.ts

## Getting started
Building deb and rpm packages requires `fakeroot` and `rpm`; run: `sudo apt-get install fakeroot rpm`
On Debian-based Linux: `sudo apt-get install build-essential g++ libx11-dev libxkbfile-dev libsecret-1-dev libkrb5-dev python-is-python3`

```sh
sudo apt-get install build-essential g++ libx11-dev libxkbfile-dev libsecret-1-dev libkrb5-dev python-is-python3

cd src
# node_v20
npm install --verbose
```

### Troubleshooting
In case of issues, try deleting the contents of `~/.node-gyp` (alternatively `~/.cache/node-gyp` for Linux, `~/Library/Caches/node-gyp/` for macOS, or `%USERPROFILE%\AppData\Local\node-gyp` for Windows) first and then run `git clean -xfd` and then try again.

Then you have two options:

- If you want to build from inside VS Code, you can open the `vscode` folder and start the build task with <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>B</kbd> (<kbd>CMD</kbd>+<kbd>Shift</kbd>+<kbd>B</kbd> on macOS). The build task will stay running in the background even if you close VS Code. If you happen to close VS Code and open it again, just resume the build by pressing <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>B</kbd> (<kbd>CMD</kbd>+<kbd>Shift</kbd>+<kbd>B</kbd>) again. You can kill it by running the `Kill Build VS Code` task or pressing <kbd>Ctrl</kbd>+<kbd>D</kbd> in the task terminal.
- If you want to build from a terminal, run `npm run watch`. This will run both the core watch task and watch-extension tasks in a single terminal.

#### Desktop

Running on Electron with extensions run in NodeJS:

##### macOS and Linux

```bash
./scripts/code.sh
./scripts/code-cli.sh # for running CLI commands (eg --version)
```

##### Windows

```bat
.\scripts\code.bat
.\scripts\code-cli.bat
```

👉 **Tip!** If you receive an error stating that the app is not a valid Electron app, it probably means you didn't run `npm run watch` first.

#### VS Code for the Web

Extensions and UI run in the browser.

👉 Besides `npm run watch` also run `npm run watch-web` to build the web bits for the built-in extensions.

##### macOS and Linux

```bash
./scripts/code-web.sh
```

##### Windows

```bat
.\scripts\code-web.bat
```

#### Code Server Web

UI in the browser, extensions run in code server (NodeJS):

##### macOS and Linux

```bash
./scripts/code-server.sh --launch
```

##### Windows

```bat
.\scripts\code-server.bat --launch
```

You can identify the development version of VS Code ("Code - OSS") by the following icon in the Dock or Taskbar:

[![VS Code default icon](https://i.imgur.com/D2CeX0y.png)](https://i.imgur.com/D2CeX0y.png)
