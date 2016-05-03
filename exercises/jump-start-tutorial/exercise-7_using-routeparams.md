# Exercise: Using RouteParams

Next up, we want to route to a contact detail page. In this exercise we're going to create a new component that is able to retreive routing parameters.

## Scenario

The contacts app should be extended with a contact detail page. We need several things to get there:

- a new route configuration
- a new method to access a single contact in our service
- a new detail component
- we need to be able to link to that new component and pass some parameters

## Tasks

1. Create a new method `getContact(id: any)` which takes an id and returns a contact by that id. (Hint: you can use [`Array#find(fn)`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find) e.g.  `this.contacts.find(contact => contact.id == id);`)
2. Create a new component `ContactDetailComponent`, using the tools you already know, with the following template:

  ```
  <div class="row">
    <div class="col s12 m7">
      <div class="card">
        <div class="card-image">
          <img [src]="INSERT_CONTACT_IMAGE">
          <span class="card-title">INSERT_CONTACT__NAME</span>
        </div>
        <div class="card-content grey-text text-darken-4">
          <div class="row">
            <span class="col s6"><i class="material-icons prefix">email</i> Email:</span>
            <span class="col s6">INSERT_CONTACT_EMAIL</span>
          </div>
          <div class="row">
            <span class="col s6"><i class="material-icons prefix">phone</i> Phone:</span>
            <span class="col s6">INSERT_CONTACT_PHONE</span>
          </div>
          <div class="row">
            <span class="col s6"><i class="material-icons prefix">cake</i> Birthday:</span>
            <span class="col s6">INSERT_CONTACT_BIRTHDAY</span>
          </div>
          <div class="row">
            <span class="col s6"><i class="material-icons prefix">public</i> Website:</span>
            <span class="col s6">INSERT_CONTACT_WEBSITE</span>
          </div>
          <fieldset>
            <legend><i class="material-icons prefix">location_city</i> Address</legend>
            <div class="row">
              <span class="col s6">Street:</span>
              <span class="col s6">INSERT_CONTACT_STREET</span>
            </div>
            <div class="row">
              <span class="col s6">Zipcode:</span>
              <span class="col s6">INSERT_CONTACT_ZIP</span>
            </div>
            <div class="row">
              <span class="col s6">City:</span>
              <span class="col s6">INSERT_CONTACT_CITY</span>
            </div>
            <div class="row">
              <span class="col s6">Country:</span>
              <span class="col s6">INSERT_CONTACT_COUNTRY</span>
            </div>
          </fieldset>
        </div>
        <div class="card-action">
          <a class="btn" [routerLink]="INSERT_DSL_FOR_CONTACT_LIST">Go Back</a>
        </div>
      </div>
    </div>
  </div>
  ```
3. Import `ContactDetailComponent` so you can use it in `ContactsApp`
4. Add a new route config to `ContactsApp` that takes `/contacts/:id` and points to `ContactDetailComponent`
5. Add names to the route configuration (`ContactsList`, `ContactDetail`)
6. Import `ROUTER_DIRECTIVES` so you can use them in `ContactsListComponent`
7. Add `ROUTER_DIRECTIVES` to `ContactsListComponent` directive dependencies
8. Change `ContactsListComponent`'s view, so that `<span>` become `<a>` and have `RouterLink` on them with a DSL configuration that points to `ContactDetailComponent`
9. Make sure that `contact.id` is passed as `id` route parameter in that configuration
10. Import `RouteParams` and `ContactsService` to use them in `ContactDetailComponent`
11. Inject `RouteParams` and `ContactsService` in `ContactDetailComponent`
12. Create a `contact` property in `ContactDetailComponent` and use `RouteParams` and `ContactsService` to retrieve the requested contact
13. Render correct `contact` properties in `ContactDetailComponent`'s view
14. Add `RouterLink` to get back to `ContactsListComponent`

### Additional resources and help

- [RouteParams](https://angular.io/docs/ts/latest/api/router/RouteParams-class.html)
