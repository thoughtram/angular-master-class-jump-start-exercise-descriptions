# Exercise: Route to your first component

The time has come! Let's implement some routing features. In this exercise we're going to route to components.

## Scenario

In order to route from our contacts list to a contact detail page, the first thing we need to do is to extract the current contacts list implementation into its own component, so that `ContactsAppComponent` is just a "frame" that holds our app, consisting of multiple components, together.

We can create a new component `ContactsListComponent` using angular-cli by running:

```
$ ng generate component contacts-list
```
Or the shorter version:
```
$ ng g c contacts-list
```


## Tasks

1. Create a component `ContactsListComponent` with angular-cli and move the current contact list logic there from `ContactsAppComponent`
2. Import `ContactsListComponent` in `src/app/app.module.ts` and add it to the module's `declarations`.
2. Create `src/app/app.routes.ts`, import the `ContactsListComponent` and export an array with routes (e.g. `export const APP_ROUTES = [...]`), holding one route pointing to `ContactsListComponent`.
3. In `app.module.ts` import `RouterModule` from `@angular/router` and `APP_ROUTES` from `./app/app.routes`
4. Add `RouterModule.forRoot(APP_ROUTES)` to the `imports` array of the module
5. Add `<router-outlet>` in `ContactsAppComponent`'s view to load and render components

## Bonus Tasks

1. Figure out how to create a route that redirects to `/` when none of the configured routes are matched by the router.

### Additional resources and help

- [Routing in Angular revisited](http://blog.thoughtram.io/angular/2016/06/14/routing-in-angular-2-revisited.html)
- [Router Guide](https://angular.io/guide/router)
- [RouterOutlet](https://angular.io/docs/ts/latest/api/router/index/RouterOutlet-directive.html)
