**JSX** is a syntax extension for JavaScript that lets you write HTML-like markup inside a JavaScript file. Although there are other ways to write components, most React developers prefer the conciseness of JSX, and most codebases use it.

**Example of JSX**

```jsx
const title = <h1> Hello React! </h1>
```

```ad-note
JSX and React are two separate things. They’re often used together, but you _can_ use them independently
```

## The Rules of JSX

1. Return a single root element
	To return multiple elements from a component, **wrap them with a single parent tag.** For example, you can use a `<div>`:

```jsx
<div>
	<h1> Hello React! </h1>
	<img  src="https://i.imgur.com/yXOvdOSs.jpg" />
</div>
```

If you don’t want to add an extra `<div>` to your markup, you can write `<>` and `</>` instead:

```jsx
<>
	<h1> Hello React! </h1>
	<img  src="https://i.imgur.com/yXOvdOSs.jpg" />
</>
```

2. Close all the tags

JSX requires tags to be explicitly closed: self-closing tags like `<img>` must become 
`<img />`, and wrapping tags like `<li>oranges` must be written as `<li>oranges</li>`.

3.  camelCase all most of the things!

```jsx
<h1 className="title"> Hello React! </h1>
```

## JSX Represents Objects

Babel compiles JSX down to `React.createElement()` calls.

These two examples are identical:

```jsx
const element = (
  <h1 className="greeting">
    Hello, world!
  </h1>
);
```

```jsx
const element = React.createElement(
  'h1',
  {className: 'greeting'},
  'Hello, world!'
);
```

`React.createElement()` performs a few checks to help you write bug-free code but essentially it creates an object or to be more precise `Fiber Node`

## Conditional Rendering 

Your components will often need to display different things depending on different conditions. In React, you can conditionally render JSX using JavaScript syntax like `if` statements, `&&`, and `? :` operators.

```jsx
function Item({ name, isPacked }) {
  if (isPacked) {
    return <li className="item">{name} ✔</li>;
  }
  return <li className="item">{name}</li>;
}
```

We can refactor previous example it this way

```jsx
return (  
	<li className="item">  
		{isPacked ? name + ' ✔' : name}  
	</li> 
);
```

Also wa can use `&&` operator

```jsx
return (  
	<li className="item">  
		{name} {isPacked && '✔'}  
	</li> 
);
```


## List Rendering

You will often want to display multiple similar components from a collection of data. You can use the JavaScript array methods to manipulate an array of data.

To render data from array you can use the `map()` array method.

```jsx
const people = [
  'Creola Katherine Johnson: mathematician',
  'Mario José Molina-Pasquel Henríquez: chemist',
  'Mohammad Abdus Salam: physicist',
  'Percy Lavon Julian: chemist',
  'Subrahmanyan Chandrasekhar: astrophysicist'
];

export default function List() {
  return (
	<ul>
	  {people.map(person =><li>{person}</li>}
    </ul>);
}
```

**Notice the sandbox above displays a console error:**

```ad-danger
Warning: Each child in a list should have a unique “key” prop.
```

You need to give each array item a `key` — a string or a number that uniquely identifies it among other items in that array:

```jsx
<li key={person.id}>...</li>
```

```ad-note
JSX elements directly inside a `map()` call always need keys!
```

Keys tell React which array item each component corresponds to, so that it can match them up later. This becomes important if your array items can move (e.g. due to sorting), get inserted, or get deleted. A well-chosen `key` helps React infer what exactly has happened, and make the correct updates to the DOM tree.

### Rules of keys

-   **Keys must be unique among siblings.** However, it’s okay to use the same keys for JSX nodes in _different_ arrays.
-   **Keys must not change** or that defeats their purpose! Don’t generate them while rendering.
