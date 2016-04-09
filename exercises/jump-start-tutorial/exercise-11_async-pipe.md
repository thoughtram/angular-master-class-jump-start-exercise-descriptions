# Exercise: Async Pipe

We can fine-tune our `ContactsApp` a little bit futher before we reached the end of this tutorial by using `AsyncPipe` in combination with our observables data structures.

## Scenario

Observable data structures can be passed directly from a component into its view and resolve by `AsyncPipe`. This makes the code a more readable since we don't have the imperative logic of resolving/subscribing to an observable. `AsyncPipe` does the job for us.

## Tasks

1. Import `Observable` from `rxjs/Observable` to use it in `ContactsListComponent`
2. Annotate the `contacts` property to be of type `Observable<Array<Contact>>`
3. Remove subscription of `contactsService.getContacts()`
4. Add `AsyncPipe` to `ngFor` expression in `ContactsListComponent`'s view

### Additional resources and help

- [Pipes - AsyncPipe](https://angular.io/docs/ts/latest/guide/pipes.html#!#the-stateful-asyncpipe-)
- [AsyncPipe](https://angular.io/docs/ts/latest/api/common/AsyncPipe-class.html)
