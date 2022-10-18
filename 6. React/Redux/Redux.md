is A Predictable State Container for JS Apps


## Motivation

As the requirements for JavaScript single-page applications have become increasingly complicated, **our code must manage more state than ever before**. This state can include server responses and cached data, as well as locally created data that has not yet been persisted to the server. UI state is also increasing in complexity, as we need to manage active routes, selected tabs, spinners, pagination controls, and so on

## Three Principles

1. **Single source of truth**, The global state of your application is stored in an object tree within a single store.
2. **State is read-only**, The only way to change the state is to emit an action, an object describing what happened.
3. **Changes are made with pure functions**, To specify how the state tree is transformed by actions, you write pure **reducers**.