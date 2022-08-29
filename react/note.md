# React

## Introduction

* The `JSX` (JavaScript XML) is an extension of JavaScript that allows DOM-like variables (=React element) to be declared.
* `Babel` compiles JSX down to React function calls. (`React.createElements()`)
* React elements are immutable.

## Components

* Components
  * JavaScript functions (props(=properties) -> React elements)
  * Good for encapsulating a part of UI that is used repetitively
* A name of user-defined component should start with a capital letter.
* Components must not changes given `props`.
  > `All React components must act like pure functions with respect to their props.`
  * Except for `controlled` components, where the values in `props` can be changed with functions from the ancestor, which will _set state_ of itself.
* Components can be "extracted" from a nested one.

## State and Lifecylcle

* State
  * = private props that is controlled by the component class.
  * can access derived props of ancestor with `getDerivedStateFromProps()`.
* Lifecycle
  1. Mounting: putting elements into DOM
    * **constructor()**
    * getDerivedStateFromProps()
    * **render()**
    * **componentDidMount()**
  2. Updating: when state or props are changed
    * getDerivedStateFromProps()
    * shouldCompoentUpdate()
    * render()
    * getSnapshotBeforeUpdate()
    * componentDidUpdate()
  3. Unmounting: when a component is removed from the DOM
    * **componentWillUnmount()**

## Handling Events

* A common pattern is for an event handler to be a method on the component class.
* `bind(this)` for event handlers must be called at `constructor()`, or use public class fields syntax in ES6.

## Conditional Rendering

* There are several ways for conditional rendering:
  * `if-else`
  * Inline `if` with logical && operator
    * `<some-condition> && <JSX>`
  * Inline `if` with conditional operator
    * `<some-condition> ? <JSX-on-true> : <JSX-on-false>`

## List and Keys

* Collections of elements can be built with `map()` functions.
* `key` attribute should be assigned on the list items as an identifier (similar to that of d3.js).
  * Usually we can use IDs of the data as keys, or index of the rendered item if stable IDs do not exist (not recommended though).
  * Rule of thumb: Elements inside the `map()` call need keys.

## Forms

* HTML form elements maintain their own state (e.g., `type`, `name`, or `value`).
* Those state `value` should be combined to the `state` of the component (controlled component).
> It seems like react implemented those forms as components with the same names.
* Add `name` attribute for `input` tag when controlling multiple inputs (from `event.target.name` value)
* Using controlled components can be tedious; there's full-fledged solutions such as [Formik](https://formik.org/).


## Lifting State up

* Rely on `the top-down data flow`,
  * by lifting the shared state up to the closest ancestor in the form of `props` if possible.
  * This will greatly reduce the surface area for bugs.
  * We can inspect the `props` and `state` values with [React Developer Tools](https://github.com/facebook/react/tree/main/packages/react-devtools).

## Composition vs. Inheritance

* Don't need to inherit classes in React. Use composition instead, with something like `props.children`.
  * `props.children` in a component contains anything inside it.
* If you need multiple _holes_ for children components, add custom attributes for each of it.

## Web Appliciation Building Process using React

> TODO
1. Break the UI into a component hierarchy
2. Build a static version in React
3. Identify the minimal (but complete) representation of UI State
4. Identify where your state should live
5. Add inverse data flow

## Miscellaneous

* NextJS = React + server-side rendering (c.f. client-side rendering)
* `arr.map(function(x) {return x * 2;});` equals to `arr.map((x) => x * 2);` in ES6.
* ES6 computed property name syntax
```js

this.setState({
  [name]: value
})

// equals to

var partialState = {};
partialState[name] = value;
this.setState(partialState);
```

* Solutions for rendering a large data set (with conditional rendering)
  * [react-window](https://github.com/bvaughn/react-window)
  * [react-virtualized](https://www.npmjs.com/package/react-virtualized)
