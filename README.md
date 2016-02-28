# Particle CLI Boilerplate

Building apps for the Particle platform (Core, Photon, Electron) using their [web IDE](https://build.particle.io) is awesome, but there are many situations where it is more convenient to use your desktop text editor, or to pull in libraries and other source code you already have on your computer.

This boilerplate repo is a template for new Particle projects, allowing you to build apps on the command line using [particle-cli](https://docs.particle.io/reference/cli/).

## Requirements

You must have a copy of `particle-cli` installed on your machine and be signed in to the Particle Cloud:

```shell
$ npm install -g particle-cli
$ particle cloud login
```

## Directory structure

### Your app code

Put your code directly into the `src` directory, or into organized subfolders inside the `src` directory, and your source will be automatically pulled in and compiled.

### Libraries

Add libraries as git submodules to the `lib` directory, and they will be automatically pulled in and built.


## Makefile commands

### Build your app

```shell
# Build a photon app (default)
$ make

# Build a core app
$ DEVICE_TYPE=core make

# Build an electron app
$ DEVICE_TYPE=electron make
```

### Flash your app via USB

Flash your app via USB, automatically putting the device into DFU mode where possible. This is the best way to flash your Particle Electron without using precious bandwidth:

```shell
$ make install-usb
```

### Flash your app via the cloud
```shell
$ DEVICE_NAME=something make install
```

### Clean up old binaries
```shell
$ make clean
```

### Make a clean build and flash via USB
```shell
$ make clean && make install-usb
```
