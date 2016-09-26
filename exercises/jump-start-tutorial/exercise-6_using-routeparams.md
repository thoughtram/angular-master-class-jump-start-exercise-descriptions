# Exercise: Accessing Route Parameters

Next up, we want to route to a contact detail page.
In this exercise we're going to create a new component that is able to retrieve routing parameters.

## Scenario

The contacts app should be extended with a contact detail page.

![a2-routing-2](https://cloud.githubusercontent.com/assets/210413/17645359/2fef4f34-6169-11e6-8da0-ff87d410044f.png)

We need several things to get there:

- a new route configuration
- a new method to access a single contact in our service
- a new detail component
- we need to be able to link to that new component and pass some parameters

## Tasks

1. Create a new method `getContact(id: number | string)` which takes an id and returns a contact by that id. (Hint: you can use [`Array#find(fn)`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find) e.g.  `this.contacts.find(contact => contact.id == id);`)
2. Create a new component `ContactsDetailComponent`, using the tools you already know, with the following template:

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
          <a class="btn" routerLink="INSERT_DSL_FOR_CONTACT_LIST">Go Back</a>
        </div>
      </div>
    </div>
  </div>
  ```
3. Add a new route to `ContactsAppRoutes` with the path `/contacts/:id` that points to `ContactsDetailComponent`
4. Change `ContactsListComponent`'s view to wrap an `<a>` around `<img>` and `<span>` and use the `RouterLink` directive with a DSL configuration that points to `ContactsDetailComponent`
5. Import and inject `ActivatedRoute` and `ContactsService` in `ContactsDetailComponent`
6. Create a `contact` property in `ContactsDetailComponent` and use `ActivatedRoute` and `ContactsService` to retrieve the requested contact
7. Render correct `contact` properties in `ContactsDetailComponent`'s view
8. Add `RouterLink` to get back to `ContactsListComponent`

### Additional resources and help

- [ActivatedRoute](https://angular.io/docs/ts/latest/api/router/index/ActivatedRoute-interface.html)
