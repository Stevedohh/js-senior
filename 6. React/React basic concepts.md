React is an open source, declarative, efficient and extremely flexible JavaScript library for creating user interfaces.

**The main React features**

- JSX allows you to manipulate the DOM directly. Whereas in jQuery, it has to be done by the developer.
- Component-based approach allows you to build encapsulated pieces of code that can be reused anywhere in the application.
- React provides a Virtual DOM to improve the perfomance of the application.
- React has a very big and involved community.

**Disadvantages of React**

-  Perfomance. Yes, React uses the Virtual DOM to update DOM and it's fast for most applications. But sometimes would be easy to update the DOM directly without Virtual DOM. For now (in 2022) we have more performant applications like Solid.js or Svelte who works without VDOM. Also, the developer must keep track of the component re-render himself, and add some optimizations such as useCallback, React.memo, useMemo. In my opinion React should keep track of this itself. At React conf 2021 the concept "React without memo" was provided, but its further fate is not known.
- React is not Reactive. React is not reactive because it does not re-render on every change. React decouples the data events from component updates. In the middle, it has a scheduler. You may `setState` a dozen times but React takes notice of which components have been scheduled to update and doesn't bother doing so until it is ready.
- Poor JSX. In React JSX you cannot use the `class` or other native html attributes. Also you cannot create custom JSX derectives as Solid.js provided.

