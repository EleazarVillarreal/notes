<image alt="Docker Logo" height="100px" src="../images/react.png" width="100px" />

# React Fundamentals

## General
* Expression slots allow you to use JavaScript expressions within JSX using the curly braces `{}`. They also allow you to add comments to your JSX. `{/* Some Comment! */}`

* In JSX, the `style` attribute accepts a JavaScript object (instead of a CSS string like in HTML), with properties written in camelCase (e.g. `backgroundColor` instead of `background-color`).

* Props are the values passed to a component (similar to HTML attributes, but can be any JavaScript value like objects, arrays, functions, etc.). Under the hood, React passes all props as a single object to the component. 

* You can assign default values directly when you destructure the object React passes to the component. The default is used only when the prop is missing or `undefined` (not when it's `null` or `0`).

* When we pass something between the open and closing tags of a component, React will automatically supply that value to us under the `children` prop.

* A React Fragment (`<>...</>`) lets you group multiple JSX elements together without adding an extra node to the DOM. This is useful because a component can only return a single element.

* When rendering a list of elements each item needs a unique `key` prop which allows React to identify which items have changed, been added, or been removed between renders, allowing it to update the DOM efficiently rather than re-rendering the entire list. 

* If your data does not have a unique identifier, use `crypto.randomUUID()` to generate one when the data is created. Avoid generating keys during rendering (e.g. inside `map()`) as this produces a new key on every render, defeating their purpose.

* Keys only need to be unique within their own array (not globally). When using a Fragment as the top-level element in a list, the shorthand `<>...</>` syntax does not support `key`, so you must switch to the long-form `<Fragment key={id}>...</Fragment>`.

* A controlled component is where React controls the value of an input via state. The input's value is set by state and updated through a setter function on every change.

* An uncontrolled component is one where the input manages its own value internally in the DOM, typically accessed via a `ref` when needed, or by reading the form data directly through a React form action using the `FormData` API.

* React uses synthetic events rather than the browser's native events. Synthetic events are React's wrapper around native events that normalize behavior across different browsers, ensuring events work consistently regardless of which browser the user is on.

* For state management, the approach depends on the type of application. Static sites can rely on React alone with Context for shared state. Client-heavy applications with complex global state benefit from a dedicated state management library like Redux. Server-heavy applications work well with React paired with a data-fetching library like SWR to handle network state.

## Patterns
* The best way to conditionally render elements in React is using a ternary operator (`condition ? <A /> : <B />`) when you need to render one thing or another, or the logical AND operator (`condition && <A />`) when you need to render something or nothing at all.

* When trying to visually hide text for screen readers a good pattern is to create a reusable `VisuallyHidden` component.
  ```
  const hiddenStyles = {
    display: 'inline-block',
    position: 'absolute',
    overflow: 'hidden',
    clip: 'rect(0 0 0 0)',
    height: 1,
    width: 1,
    margin: -1,
    padding: 0,
    border: 0,
  };

  function VisuallyHidden({ children }) {
    return (
      <span style={hiddenStyles}>
        {children}
      </span>
    );
  }

  export default VisuallyHidden;
  ```

## Hooks
* `useState` is a React Hook that lets you add state to a component. It returns an array of exactly two values, the current state and a setter function, which are destructured using the convention `const [something, setSomething] = useState(initialValue)`.

* The setter function returned by `useState` is asynchronous. Calling it does not immediately update the state variable. Instead, React queues the state change and re-renders the component with the new value on the next render. This means reading the state variable immediately after calling the setter will still return the old value.

* State should never be mutated directly. Instead, always pass a new value to the setter function. Mutating state directly will not trigger a re-render, leaving the UI out of sync with the underlying data. For objects and arrays, this means creating a new copy with the updated values rather than modifying the existing one.

* If the initial state requires an expensive calculation, you can pass an initializer function instead of a value directly. React will only call it once on the initial render rather than on every re-render.

  ```jsx
    const [state, setState] = useState(() => {
      // Some expensive calculation...
      return someExpensiveValue;
    });
  ```

