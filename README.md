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

## Problems

After installing electron, I got the following error:

```
$ electron -v
/usr/local/lib/node_modules/electron-prebuilt/dist/electron: error while loading shared libraries: libgconf-2.so.4: cannot open shared object file: No such file or directory
```

Solution:

```bash
sudo apt-get install libgconf-2-4
```