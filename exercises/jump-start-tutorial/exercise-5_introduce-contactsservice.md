# Exercise: Building a service and using DI

A static list of data is just okay to try some things out or for demo purposes. However, in a real world app, we surely don't want to rely on static data, but rather have a service that takes care of provide the data we need, no matter where it comes from.

In this exercise we're going to learn how to create services and how to inject them into our application using providers.

## Scenario

`CONTACT_DATA` is an implementation detail we don't want to rely on in `ContactsApp`. Create a service called `ContactsService` using angular-cli by running:

```
$ ng generate service contacts-service
```
Or the shorter version:
```
$ ng g service contacts-service
```

This will create a file in `src/client/app/contacts-service/contacts-service.ts`. Implement a method `getContacts()` that simply returns the collection of `CONTACT_DATA` for us. Use that new service by adding a provider to `bootstrap()` and injecting it into `ContactsApp`.
Our app should render the same, it's just the inner architecture that has changed.


## Tasks

1. Create a `ContactsService` using angular-cli
2. Import `CONTACT_DATA`
3. Create a method `getContacts()` which returns the given data
4. Add `ContactsService` provider to `ContactsApp`'s `providers` property to make the service available in your app
5. Inject `ContactsService` in `ContactsApp`
6. Use `ContactsService#getContacts()` to retrieve the contacts data

### Additional resources and help

- [Dependency Injection in Angular 2](http://blog.thoughtram.io/angular/2015/05/18/dependency-injection-in-angular-2.html)
- [Dependency Injection (angular.io)](https://angular.io/docs/ts/latest/guide/dependency-injection.html)
