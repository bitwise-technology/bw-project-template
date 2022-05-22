# Naming conventions

## Variables 

Here should have a short description of which pattern naming variables should follow and why.

Ex1:

The arrays or any type of list should contain the prefix list on the end:

```ts
//Arrays
let userList: string[] = ['John', 'Jane', 'Bob'];
```

Ex2:

The arrays or any type of list should avoid prefixes and use the plural form:

```ts
//Arrays
let users: string[] = ['John', 'Jane', 'Bob'];
```

## Functions

Here should have a short description of which pattern naming functions/methods should follow and why.

Ex: 

The methods should respect the following rules:

- Names are case-sensitive, lowercase and uppercase are different.
- Start function names with a letter, use camelCase for names.
- Use descriptive names, usually verbs in the imperative form.
- Do not use short or acronym names, with a few exceptions like (x, y, z)
- Common prefixes are get, make, apply, calculate, compute etc.


```tsx
// VERBE-IN-IMPERATIVE-NAME
function getName() {
  return 'John';
}
```
