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
* Components must not changes given props.
  > `All React components must act like pure functions with respect to their props.`

# State and Lifecylcle

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

## Notations

* browser DOM elements <-> React elements
* stateful/stateless components

## Miscellaneous

* NextJS = React + server-side rendering (c.f. client-side rendering)

