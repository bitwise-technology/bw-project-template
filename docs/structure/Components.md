# Components

This file should contain how our component is structured, tested and added to the repository. 

Follow the topics example bellow:

## General concepts

Here's the usual structure for a component. Basically, we should inform the devs:
- How the folders structure looks like
- How import and export the components into the code repository
- Examples of how to test components
- 

Example of how to explain a folder structure:

```tsx
- components
    | - Navigation
        | - Header.component.jsx
        | - Footer.component.jsx
    | - Cards
        | - Confirm.card.jsx
        | - Checkout.card.jsx

- pages
    | - Auth
        | - Sign-up.jsx
        | - Login.jsx
```

Example in how to explain an export:
```tsx
// modules/components/MyComponent/MyComponent.tsx
export const MyComponent = (props: Props) => { ... }
```


## Reusable Component

Explain how and when the dev should worry about refactor a component to be reusable. This will avoid premature optimization and make the code more readable.
If you prefer you can create a dedicated file to explain the guidelines for reusable components or even for reusable code and refactor like ```Refactor & Optimize.md```
