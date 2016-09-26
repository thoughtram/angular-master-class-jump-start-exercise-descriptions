# Exercise: Route to your first component

The time has come! Let's implement some routing features. In this exercise we're going to route to components.

## Scenario

In order to route from our contacts list to a contact detail page, the first thing we need to do is to extract the current contacts list implementation into its own component, so that `ContactsAppComponent` is just a "frame" that holds our app, consisting of multiple components, together.

We can create a new component `ContactsListComponent` using angular-cli by running:

```
$ ng generate component --nospec contacts-list
```
Or the shorter version:
```
$ ng g c --nospec contacts-list
```


## Tasks

1. Create a component `ContactsListComponent` with angular-cli and move the current contact list logic there from `ContactsAppComponent`
2. Create `src/app/app.routes.ts`, import the `ContactsListComponent` from `./contacts-list` and export an array with routes (e.g. `export const ContactsAppRoutes = [...]`), holding one route pointing to `ContactsListComponent`.
3. In `app.module.ts` import `RouterModule` from `@angular/router` and `ContactsAppRoutes` from `./app/app.routes`
4. Add `RouterModule.forRoot(ContactsAppRoutes)` to the `imports` array of the module
5. Add `<router-outlet>` in `ContactsAppComponent`'s view to load and render components

### Additional resources and help

- [Router Guide](https://angular.io/docs/ts/latest/guide/router.html)
- [provideRouter](https://angular.io/docs/ts/latest/api/router/index/provideRouter-function.html)
- [ROUTER_DIRECTIVES](https://angular.io/docs/ts/latest/api/router/index/ROUTER_DIRECTIVES-let.html)
- [RouterOutlet](https://angular.io/docs/ts/latest/api/router/index/RouterOutlet-directive.html)
