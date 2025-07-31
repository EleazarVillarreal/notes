<image alt="Docker Logo" height="100px" src="./images/joy-of-react.png" width="100px" />

# The Joy of React

## React Fundamentals

* Expression slots allow you to use JavaScript expressions within JSX using the curly braces `{}`. They also allow you to add comments to your JSX. `{/* Some Comment! */}`
* It's possible to set attributes to `true` by specifying only the key as a property in a JSX element.
* The best way to use fallback values for props is to use default values instead of `||` or `??` in the component itself.
* The `||` operator will occasionally surprise us by using the default value even when we've supplied a value. This can happen when the supplied value is `falsy`.
* The `??` operator only guards against `nullish` values (`null` and `undefined`). It means we don't have to worry about “surprising” `falsy` values like `0`.
* When using fragments, it's sometimes required to switch to the long-form `React.Fragment`, so that we can apply a key. `<React.Fragment key={unique.id}>`
* Keys only have to be unique within their array and not globally unique across the entire applications.
* You can use "control flow" operators for conditional logic within a React component.
* The `&&` operator is a “control flow” operator because, like if/else, it will always result in one of two paths being taken. 
* Always use boolean values with `&&` because JSX will display the number `0` if your expression evaluates to `0` which may cause unexpected results. 
* The `!!` can convert any non-boolean value to a boolean if needed.
* If you need to display different content depending on a condition then you can use a ternary operator. `condition ? firstExpression : secondExpression`

  ```typescript
  // Simple range utility function that will return an array
  const range = (start, end, step = 1) => {
    let output = [];

    if (typeof end === 'undefined') {
      end = start;
      start = 0;
    }

    for (let i = start; i < end; i += step) {
      output.push(i);
    }

    return output;
  };
  ```

  ## Working With State

* The `useState` hook is a special type of function that allows us to "hook into" React internals. It returns an array containing the current value of the state, and a function that allows us to update the state variable.
* The useState hook can take in an anonymous method that will only run on the very first render to calculate the initial value. <br/> 
Ex: `useState(() => { return window.localStorage.getItem('saved-count') });`
* If you call a function within the useState as its default value instead of using an anonymous function the function will be called at every render.
* State setters are asynchronous, so they do not update the state immediately.
* Core React Loop - Mount → Trigger → Render (Reconcile) → Commit
* Not all re-renders require re-paints! If nothing has changed between snapshots, React won't edit any DOM nodes, and nothing will be re-painted.