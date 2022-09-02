# [Create React App](https://github.com/facebook/create-react-app)

## Prerequisite

* `node.js`
  * JavaScript runtime environment. executes JS code outside of a web browser
* `npm` (node package manager)
  * A package manager for modules based on `node.js`
* `npx` (node package _execute_)
  * A tool installed along with `npm@5.2.0`

## Quick Start

* No need to install or configure tools like webpack or Babel

```bash
npx create-react-app my-app
cd my-app
npm start

# Check http://localhost:3000/
```

## Folder Structure

* Necessary files to build
  * `public/index.html`
  * `src/index.js`
* Must put JS and CSS files inside `src` directory, otherwise webpack won't see them.
