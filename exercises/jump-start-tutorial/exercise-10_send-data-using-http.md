# Exercise: Send data using http

In the last exercise we've extended our `ContactsApp` to fetch its data from a remote server. In this exercise we're going to explore how to send data using http.

## Scenario

We still have to add http capabilities to our `ContactEditorComponent`, since it has to **send** data when we update a contact, which we haven't done until now.

## Tasks

1. Import `Headers` in `ContactsService`
2. Create headers using the `Headers` constructor á la

  ```
  let headers = new Headers({'Content-Type': 'application/json;charset=UTF-8'});
  ```

  Don't worry about the bad ergonomics for now. This will be fixed in later releases.
3. Teach `updateContact(contact: Contact)` to use `Http.put(url, data, headers)`, to send the contact that has to be updated over the wire.

  - The endpoint is `localhost:4200/api/contacts/{$id}`
  - Make sure to use `PUT` method
  - You can serialize the contact data using `JSON.stringify(object)`

4. Use `ContactsService#updateContact` in `ContactEditorComponent#save()`

### Additional resources and help
- [Angular 2 Developer Guide: Server Communication](https://angular.io/docs/ts/latest/guide/server-communication.html)
- [Taking advantage of Observables in Angular 2](http://blog.thoughtram.io/angular/2016/01/06/taking-advantage-of-observables-in-angular2.html)
- [Taking advantage of Observables in Angular 2 - Part 2](http://blog.thoughtram.io/angular/2016/01/07/taking-advantage-of-observables-in-angular2-pt2.html)
