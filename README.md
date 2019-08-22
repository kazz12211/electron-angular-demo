# ElectronAngularDemo

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 8.1.2.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `--prod` flag for a production build.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via [Protractor](http://www.protractortest.org/).

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md).


## Install Electron

In terminal, execute the following command.

```
$ cd project_root_dir
$ npm i --save-dev electron@latest
```

## Write bootstrap script file

Add main.js (in this case) to project root directory.

## Edit package.json for electron

```
 "name": "electron-angular-demo",
  "version": "0.0.0",
  "main": "main.js",  <== specify bootstrap script file
  "scripts": {
    "ng": "ng",
    "start": "ng serve",
    "build": "ng build",
    "test": "ng test",
    "lint": "ng lint",
    "e2e": "ng e2e",
    "start:electron": "ng build --base-href ./ && ./node_modules/electron/dist/electron .", <== build and run command
    "electron": "./node_modules/electron/dist/electron ." <== run electron
  },
```

## To build electron app with Typescript compiler

Edit tsconfig.json to use "es5" target compiler option.

```
"compilerOptions": {
    "baseUrl": "./",
    "outDir": "./dist/out-tsc",
    "sourceMap": true,
    "declaration": false,
    "downlevelIteration": true,
    "experimentalDecorators": true,
    "module": "esnext",
    "moduleResolution": "node",
    "importHelpers": true,
    "target": "es5", <== Modification
    "typeRoots": [
      "node_modules/@types"
    ],
    "lib": [
      "es2018",
      "dom"
    ]
  },
 ```


 ## To suppress security warning

 Add the following line in main.js.

```
 process.env['ELECTRON_DISABLE_SECURITY_WARNINGS'] = 'true';
```