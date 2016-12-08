# Exercise: Two-way data binding and sending data

Combining property binding with event binding results in two-way data binding. This exercise demonstrates how `ngModel` and two-way data binding can be used to create our first simple form.

In the last exercise we've extended our `ContactsAppComponent` to fetch its data from a remote server. In this exercise we're going to explore how to send data using http.

## Scenario

Displaying details of a contact is nice, but we also want to be able to edit them. We want to take advantage of Angular 2's `ngModel` directive that implements two-way data binding to build our first form.

This form displays a `contact` but allows for editing that contact at the same time. We have to add http capabilities to our `ContactsEditorComponent`, since it has to **send** data when we update a contact.

## Tasks

1. Create a new component `ContactsEditorComponent` using the tools you already know with the following template:

  ```
  <div class="row">
    <form class="col s12 m7">
      <div class="card">
        <div class="card-image">
          <img [src]="INSERT_CONTACT_IMAGE">
          <span class="card-title">{{contact.name}}</span>
        </div>
        <div class="card-content grey-text text-darken-4">
          <div class="row">
            <div class="input-field col s12">
              <i class="material-icons prefix">account_circle</i><input id="name" name="name" type="text" class="validate">
              <label class="active" for="name">Name</label>
            </div>
          </div>
          <div class="row">
            <div class="input-field col s12">
              <i class="material-icons prefix">email</i><input id="email" name="email" type="text" class="validate">
              <label class="active" for="email">Email</label>
            </div>
          </div>
          <div class="row">
            <div class="input-field col s12">
              <i class="material-icons prefix">phone</i><input id="phone" name="phone" type="text" class="validate">
              <label class="active" for="phone">Phone</label>
            </div>
          </div>
          <div class="row">
            <div class="input-field col s12">
              <i class="material-icons prefix">cake</i><input id="birthday" name="birthday" type="date" class="validate">
              <label class="active" for="phone">Birthday</label>
            </div>
          </div>
          <div class="row">
            <div class="input-field col s12">
              <i class="material-icons prefix">public</i><input id="website" name="website" type="text" class="validate">
              <label class="active" for="phone">Website</label>
            </div>
          </div>
          <fieldset>
            <legend><i class="material-icons prefix">location_city</i> Address</legend>

            <div class="row">
              <div class="input-field col s12">
                <input id="street" name="street" type="text" class="validate">
                <label class="active" for="street">Street</label>
              </div>
            </div>
            <div class="row">
              <div class="input-field col s12">
                <input id="zip" name="zip" type="text" class="validate">
                <label class="active" for="zip">Zipcode</label>
              </div>
            </div>

            <div class="row">
              <div class="input-field col s12">
                <input id="city" name="city" type="text" class="validate">
                <label class="active" for="city">City</label>
              </div>
            </div>
            <div class="row">
              <div class="input-field col s12">
                <input id="country" name="country" type="text"  class="validate">
                <label class="active" for="country">Country</label>
              </div>
            </div>
          </fieldset>
        </div>
        <div class="card-action">
          <button type="button" class="btn" (click)="cancel(contact)">Cancel</button>
          <button type="button" class="btn" (click)="save(contact)">Save</button>
        </div>
      </div>
    </form>
  </div>
  ```
2. Import `FormsModule` from `@angular/forms` and add it to the `imports` array of the application module
3. Add a new route to `ContactsAppRoutes` that takes `/contact/:id/edit` and points to `ContactsEditorComponent`
4. Add a button with `RouterLink` to `ContactsDetailComponent`'s view that routes to `ContactsEditorComponent` and passes `contact.id` as `id` route parameter
5. Add `*ngIf="contact"` to the button since the safe navigation operator can't be used here
6. Teach `ContactsService` a method `updateContact(contact: Contact)`, that uses `Http.put(url, data)` to send the contact that has to be updated over the wire.

  - The endpoint is `localhost:4200/api/contacts/${id}`
  - Make sure to use `PUT` method

7. Inject `ContactsService`, `ActivatedRoute` and `Router` into `ContactsEditorComponent`
8. Create a `contact` property and Use `ContactsService#getContact()` in `ngOnInit()` to fetch the contact object.
9. Make sure to initialize `contact: Contact = <Contact>{ address: {}};` in `ContactsEditorComponent` since the safe navigation operator can't be used with `ngModel`
10. Render `contact` properties using `ngModel` in `ContactsEditorComponent`'s view
11. Implement a method `cancel(contact: Contact)` in `ContactsEditorComponent` that navigates to `ContactsDetailComponent` of the given contact using `Router#navigate()` (takes a router dsl configuration)
12. Implement a method `save(contact: Contact)` in `ContactsEditorComponent` that uses`ContactsService#updateContact` and navigates back to `ContactsDetailComponent` as soon as the `PUT` request was succesful.

## Bonus Tasks:

1. Currently the api endpoint is hard-coded right into `ContactsService`. Can you find a way to make it injectable throughout your application? Give it a try!

(hint: we need **string token** e.g. "API_ENDPOINT" and a new decorator called `@Inject`)

2. Because "API_ENDPOINT" is a very generic name, we want to make sure to not run into naming collisions. Find out how you can use `OpaqueToken` and refactor the previous implementation.

3. With the `API_ENDPOINT` and the `ContactsService` we already have two of our own providers that we use across the application. Let's combine those and share via a single token `APP_PROVIDERS`.

### Additional resources and help

- [ngModel](https://angular.io/docs/ts/latest/api/common/index/NgModel-directive.html)
- [Router#navigate()](https://angular.io/docs/ts/latest/api/router/index/Router-class.html#!#navigate-anchor)
- [Angular 2 Developer Guide: Server Communication](https://angular.io/docs/ts/latest/guide/server-communication.html)
- [Taking advantage of Observables in Angular 2](http://blog.thoughtram.io/angular/2016/01/06/taking-advantage-of-observables-in-angular2.html)
- [Taking advantage of Observables in Angular 2 - Part 2](http://blog.thoughtram.io/angular/2016/01/07/taking-advantage-of-observables-in-angular2-pt2.html)
