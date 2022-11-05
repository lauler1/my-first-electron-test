# my-first-electron-test

This is a test project for electron

---

## Instructions

I folowed this [tutorial](https://www.tutorialspoint.com/electron/electron_installation.htm)

To install electron:
```bash
$ sudo npm install -g electron
```
The `-g` means globaly, therefore it needs the `sudo`.

Alternatively, it can be installed using this instruction from the electron official page:

```bash
$ npm i -D electron@alpha
```

To run it, use:
```bash
$ electron ./main.js
```

You can use Bower to manage these front-end dependencies. Install bower using:

```bash
$ npm install -g bower
```

To get the latest stable version of bootstrap, enter the following command:

```bash
$ bower install bootstrap
```

Let us now install jquery using the npm command:

```bash
$ npm install --save jquery
```

### Packaging Apps

```bash
# for use in npm scripts
$ npm install electron-packager --save-dev
```

```bash
# for use from cli
$ npm install electron-packager -g
```

In this section, we will see how to run the packager from the command line. The basic form of the command is:

```bash
electron-packager <sourcedir> <appname> --platform=<platform> --arch=<arch> [optional flags...]
```

This will:

Find or download the correct release of Electron.

Use that version of Electron to create a app in `<output-folder>/<appname>-<platform>-<arch>`.

`--platform` and `--arch` can be omitted, in two cases. If you specify `--all` instead, bundles for all valid combinations of target platforms/architectures will be created. Otherwise, a single bundle for the host platform/architecture will be created.

E.g.:
```bash
$ electron-packager . my-first-electron-test

$ electron-packager . my-first-electron-test --platform=linux arch=x64

$ electron-packager . my-first-electron-test --platform=win32

$ electron-packager . my-first-electron-test --platform=win32 --arch=ia32

$ electron-packager . electron-tutorial-app --overwrite --asar=true --platform=linux --arch=x64 --icon=assets/icons/png/1024x1024.png --prune=true --out=release-builds
```

---


## Problems

### Electron installation problem

After installing electron, I got the following error:

```
$ electron -v
/usr/local/lib/node_modules/electron-prebuilt/dist/electron: error while loading shared libraries: libgconf-2.so.4: cannot open shared object file: No such file or directory
```

Solution:

```bash
sudo apt-get install libgconf-2-4
```

### JQuery `require` problem

From this [forum](https://stackoverflow.com/questions/44391448/electron-require-is-not-defined), as of version 5, the default for `nodeIntegration` changed from true to false. You can enable it when creating the Browser Window:

```js
   win = new BrowserWindow({
    width: 800,
    height: 600,
    webPreferences: {
      nodeIntegration: true,
      contextIsolation: false
  }})
```

### `fs.appendFile` without callback

In the tutorial, fs.appendFile had no callback which generated an error. Callback is mandatory.
```js
   fs.appendFile('contacts', name + ',' + email + '\n', (err) => {
    if (err) {
      console.log(err);
    }})
```

