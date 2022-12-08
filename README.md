# Angular Cli + Electron

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 15.0.3.

The Angular project is wrapped in an Electron environment, that enables you to start the application in a separate window on your desktop.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The application will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via a platform of your choice. To use this command, you need to first add a package that implements end-to-end testing capabilities.

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli).

## Add support for file system ([no official support](https://github.com/angular/angular-cli/issues/4227)):

Create a file called `native.js` in the `src` folder and insert the following:

```js
window.fs = require("fs");
```

Add this file to the `.angular-cli.json` scripts array:

```json
"scripts": [
    "native.js"
],
```

Add the following lines to `polyfills.ts`:

```ts
declare global {
  interface Window {
    fs: any;
  }
}
```

After that you can access the filesystem with:

```ts
window.fs.writeFileSync("sample.txt", "my data");
```

See this [pull request](https://github.com/PKief/angular-cli-electron/pull/1/files) to follow the changes.
