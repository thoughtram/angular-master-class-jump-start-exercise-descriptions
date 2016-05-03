# Exercise: Display list of contacts

The goal of this exercise is to explore and discuss how we create lists dynamically based on data collections that derived from a component's property. Let's create a list of contacts.

## Scenario

In order to render a list of contacts, we need data that we can actually work with. Take a look at `src/client/app/data/contact-data.ts`. What you'll find is a data collection of contacts.

```
export const CONTACT_DATA = [
  {
    id: 0,
    name: 'Christoph Burgdorf',
    birthday: 1980-01-01',
    email: 'emailaddress',
    phone: '_49 000 1111',
    website: 'thoughtram.io',
    image: '/images/0.jpg',
    address: {
      street: 'thoughtram road 1',
      zip: '65222',
      city: 'Hanover',
      country: 'Germany'
    }
  },
  {
    id: 1,
    name: 'Pascal Precht',
    birthday: 1980-01-01',
    email: 'emailaddress',
    phone: '_49 000 1111',
    website: 'thoughtram.io',
    image: '/images/1.jpg',
    address: {
      street: 'thoughtram road 1',
      zip: '65222',
      city: 'Hanover',
      country: 'Germany'
    }
  },
  ...
```

Import that data, assign it a `contacts` property of `ContactsApp` and use the `ngFor` directive to render a HTML list, based on that data, in `ContactsApp`'s view.

## Tasks

1. Import `CONTACT_DATA`
2. Create a property `contacts` in `ContactsApp` and assign the collection.
3. Extend the existing static list in `ContactsApp`'s view with `ngFor` and render a list item for each contact in the collection.

### Additional resources and help

- [NgFor](https://angular.io/docs/ts/latest/api/common/NgFor-directive.html)
