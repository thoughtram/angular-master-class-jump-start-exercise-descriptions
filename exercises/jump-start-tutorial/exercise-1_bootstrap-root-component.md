# Exercise: Bootstrap your first Angular 2 App

The goal of this exercise is to get you started with Angular 2 by bootstrapping your first app. It's purpose is mainly to familiarize yourself with the Angular 2 bootstrap process.

## Scenario

In `src/client/app/contacts-app.ts` you'll find the import statement:

```
import {Component} from 'angular2/core';
```

And in `src/client/app.ts` you'll find:

```
import {bootstrap} from 'angular2/platform/browser';
import {ContactsApp} from './app/contacts-app';
```

Use the the `@Component()` decorator to build a `ContactsApp` component, and the `bootstrap()` function to bootstrap that component. The component should have a template that simply displays "Hello World". Don't forget to specify a `selector` (e.g. `contacts-app`) which you'll use in `app/index.html` as root host element.

## Tasks

1. Create a class `ContactsApp` and export it using `export`
2. Decorate `ContactsApp` with `@Component()` decorator
3. Give component an appropriate selector (e.g. `contacts-app`)
4. Define a template on the component that displays "Hello World"
5. Use given selector as tag in `index.html`
6. Bootstrap `ContactsApp` using `bootstrap()`

### Additional resources and help

This project can be run using the angular-cli. Once installed using

```
$ npm install -g angular-cli
$ cd path/to/angular2-master-class-exercises
$ npm install
```
you can compile, build and run the app using

```
$ ng serve
```

This will transpile the TypeScript source code and spins up a web server on `localhost:4200`, where you can see the running app.

#### API Documentation

- [ComponentFactory](https://angular.io/docs/ts/latest/api/core/ComponentFactory-interface.html)
- [bootstrap](https://angular.io/docs/ts/latest/api/platform/browser/bootstrap-function.html)
