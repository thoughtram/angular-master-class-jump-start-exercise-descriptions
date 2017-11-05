# Exercise: Display list of contacts

The goal of this exercise is to explore and discuss how we create lists dynamically based on data collections that derived from a component's property. Let's create a list of contacts.

## Scenario

In order to render a list of contacts, we need data that we can actually work with. Take a look at `src/app/data/contact-data.ts`. What you'll find is a data collection of contacts.

```
export const CONTACT_DATA = [
  {
    id: 0,
    firstname: 'Christoph',
    lastname: 'Burgdorf',
    street: 'thoughtram road 1',
    zip: '65222',
    city: 'Hanover',
    image: '/images/0.jpg'
  },
  {
    id: 1,
    firstname: 'Pascal',
    lastname: 'Precht',
    street: 'thoughtram road 1',
    zip: '65222',
    city: 'Hanover',
    image: '/images/1.jpg'
  },
  ...
```

Import that data, assign it a `contacts` property of `ContactsAppComponent` and use the `ngFor` directive to render a HTML list, based on that data, in `ContactsAppComponent`'s view.

## Tasks

1. Import `CONTACT_DATA`
2. Create a property `contacts` in `ContactsAppComponent` and assign the collection.
3. Extend the existing static list in `ContactsAppComponent`'s view with `ngFor` and render a list item for each contact in the collection.

## Bonus Tasks

1. Figure out what `ngFor`'s `trackBy` property is about and use it to make `ngFor` track the list by the contact ids.

### Additional resources and help

- [NgFor](https://angular.io/guide/template-syntax#ngfor)
