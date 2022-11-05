# my-first-electron-test

This is a test project for electron


# Instructions

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

### JQuery `require`problem

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

