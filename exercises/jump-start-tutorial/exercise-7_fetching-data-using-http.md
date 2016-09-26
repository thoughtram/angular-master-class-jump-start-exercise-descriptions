# Exercise: Fetching data using Http

In this exercise we're going to replace our static `CONTACT_DATA` with actual http requests to fetch the data from a remote web server.

## Scenario

Until now we've worked with static (mock) data provided by collection via our `ContactsService`. We now want to take it one step further and fetch this data from a server using Angular's `Http` layer.

In order to make http work, we need to configure our application's dependency injector and teach it some http capabilities. Just like for the router, Angular provides a module `HttpModule` that we have to import from `@angular/http`.

We also need to import operators for the Reactive Extensions. In this exercise we're mainly interested in the `map()` function which we can import from `rxjs/add/operator/map`.

Use these new tools to extend `ContactsService` to use `Http` and fetch the contacts data from `http://localhost:4201/api`. 

## Tasks

1. Run `npm run rest-api` from another terminal session to start the REST API server
2. Import `HttpModule` from `@angular/http` and add it to the `imports` array of our module
3. Import `rxjs/add/operator/map` (No named imports needed!)
4. Import `Http` and inject it into `ContactsService`
5. Create a property `API_ENDPOINT` with the value of `http://localhost:4201` in `ContactsService`
6. Change `getContacts()` so that it uses `Http.get()` to fetch contacts data from `http://localhost:4201/api/contacts`.
7. Do the same for `getContact()`. Keep in mind that this API expects a parameter (`http://localhost:4201/api/contacts/${id}`
8. Change `ContactsService` usage in `ContactsDetailComponent` and `ContactsListComponent` since it's now based on observables
9. Fix rendering in `ContactsDetailComponent`'s view using safe navigation operator (`contact?.[PROPERTY]`)

## Bonus Tasks

You might notice that the image in `ContactsDetailComponent` cause `404` errors. Can you find a solution for it?

## REST API Server

Since your Angular 2 application will request data from `http://localhost:4201/api`, you will need a local server to respond to the REST API calls. 

You have to first start the server in a terminal seperate session: **`npm run rest-api`**.

> And, of course, you use a separate terminal session to launch your web application:  **`ng serve`**.

### Additional resources and help

- [HTTP_PROVIDERS](https://angular.io/docs/ts/latest/api/http/index/HTTP_PROVIDERS-let.html)
- [Http](https://angular.io/docs/ts/latest/api/http/index/Http-class.html)
- [Angular 2 Developer Guide: Server Communication](https://angular.io/docs/ts/latest/guide/server-communication.html)
- [Taking advantage of Observables in Angular 2](http://blog.thoughtram.io/angular/2016/01/06/taking-advantage-of-observables-in-angular2.html)
- [Taking advantage of Observables in Angular 2 - Part 2](http://blog.thoughtram.io/angular/2016/01/07/taking-advantage-of-observables-in-angular2-pt2.html)
- [Template Syntax - Elvis Operator](https://angular.io/docs/ts/latest/guide/template-syntax.html#!#the-elvis-operator-and-null-property-paths)
