Plain Email
==============

An app concept for efficient one-touch email processing workflow

![Screenshot](http://www.plainemail.com/images/screenshot.png)

# Quick start
The only development dependency of this project is [Node.js](https://nodejs.org). So just make sure you have it installed.

Then type few commands known to every Node developer...

```
npm install
npm start
```

... and boom! You have Plain Email running.

# Structure of the project

There are **two** `package.json` files:  

#### 1. For development
Sits on path: `plain-email/package.json`. Here you declare dependencies for your development environment and build scripts. **This file is not distributed with the release!**

#### 2. For the application
Sits on path: `plain-email/app/package.json`. This is **real** manifest of the app.

### Project's folders

- `app` - code of the application.
- `config` - place for you to declare environment specific stuff.
- `build` - in this folder lands built, runnable application.
- `releases` - ready for distribution installers will land here.
- `resources` - resources for particular operating system.
- `tasks` - build and development environment scripts.


# Development

#### Installation

```
npm install
```
It will also download Electron runtime, and install dependencies for second `package.json` file inside `app` folder.

#### Starting the app

```
npm start
```

#### Adding pure-js npm modules to your app

Remember to add your dependency to `app/package.json` file, so do:

```
cd app
npm install name_of_npm_module --save
```

#### Adding native npm modules to your app

If you want to install native module you need to compile it agains Electron, not Node.js you are firing in command line by typing `npm install` [(Read more)](https://github.com/atom/electron/blob/master/docs/tutorial/using-native-node-modules.md).

```
npm run app-install -- name_of_npm_module
```

Of course this method works also for pure-js modules, so you can use it all the time if you're able to remember such an ugly command.

#### Unit tests

This project uses [jasmine](http://jasmine.github.io/2.0/introduction.html) unit test runner. To run it go with standard:

```
npm test
```

You don't have to declare paths to spec files in any particular place. The runner will search through the project for all `*.spec.js` files and include them automatically.


# Making a release

**Note:** There are various icon and bitmap files in `resources` directory. Those are used in installers and are intended to be replaced by your own graphics.

To make ready for distribution installer use command:

```
npm run release
```

It will start the packaging process for operating system you are running this command on. Ready for distribution file will be outputted to `releases` directory.

You can create Windows installer only when running on Windows, the same is true for Linux and OSX. So to generate all three installers you need all three operating systems.

At the moment only the OSX installer is built properly.

I'm going to try, if I can get it to work on Linux ((K)Ubuntu 18.04)
