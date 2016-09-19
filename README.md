# babel-plugin-inline-react-svg

Transforms imports to SVG files into React Components, and optimizes the SVGs with [SVGO](https://github.com/svg/svgo/).

For example, the following code...

```jsx
import React from 'react';
import CloseSVG from './close.svg';

export default const MyComponent = () => <CloseSvg />;
```

will be transformed into...

```jsx
import React from 'react';
const CloseSVG = () => <svg>{* ... *}</svg>;

export default const MyComponent = () => <CloseSvg />;
```

## Installation

```
npm install --save-dev babel-plugin-inline-react-svg
```

## Usage

### Via `.babelrc` (Recommended)

**.babelrc**

```json
{
  "plugins": [
    "inline-react-svg"
  ]
}
```

### Via CLI

```sh
$ babel --plugins inline-react-svg script.js
```

### Via Node API


```javascript
require('babel-core').transform('code', {
  plugins: ['inline-react-svg']
}) // => { code, map, ast };
```

---

Inspired by and code foundation provided by [react-svg-loader](https://github.com/boopathi/react-svg-loader).