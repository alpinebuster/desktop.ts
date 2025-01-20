# desktop.ts

## Getting started
Building deb and rpm packages requires `fakeroot` and `rpm`; run: `sudo apt-get install fakeroot rpm`
On Debian-based Linux: `sudo apt-get install build-essential g++ libx11-dev libxkbfile-dev libsecret-1-dev libkrb5-dev python-is-python3`

```sh
sudo apt-get install build-essential g++ libx11-dev libxkbfile-dev libsecret-1-dev libkrb5-dev python-is-python3

cd src
npm install --verbose

git clean -xfd
```

### Troubleshooting
In case of issues, try deleting the contents of `~/.node-gyp` (alternatively `~/.cache/node-gyp` for Linux, `~/Library/Caches/node-gyp/` for macOS, or `%USERPROFILE%\AppData\Local\node-gyp` for Windows) first and then run `git clean -xfd` and then try again.

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
