<image alt="Docker Logo" height="100px" src="../images/react.png" width="100px" />

# React Fundamentals

## General
* Expression slots allow you to use JavaScript expressions within JSX using the curly braces `{}`. They also allow you to add comments to your JSX. `{/* Some Comment! */}`
* In JSX, the `style` attribute accepts a JavaScript object (instead of a CSS string like in HTML), with properties written in camelCase (e.g. `backgroundColor` instead of `background-color`).
* Props are the values passed to a component (similar to HTML attributes, but can be any JavaScript value — objects, arrays, functions, etc.). Under the hood, React passes all props as a single object to the component. You can assign default values directly when you destructure the object React passes to the component — the default is used only when the prop is missing or `undefined` (not when it's `null` or `0`).
* When we pass something between the open and closing tags of a component, React will automatically supply that value to us under the `children` prop.
* A React Fragment (`<>...</>`) lets you group multiple JSX elements together without adding an extra node to the DOM. This is useful because a component can only return a single element.