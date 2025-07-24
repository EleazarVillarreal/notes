<image alt="React State Logo" height="100px" src="./images/state-management.png" width="100px" />

# State Management

## Derived State
* Rule: If you can calculate (derive) state, don't store it.
* Anti-Pattern: Using `useState` + `useEffect` to sync derived data.
* Best practice: Calculate derived values directly in render or with useMemo.

### Benefits:
* Eliminates synchronization bugs.
* Reduces state complexity.
* Automatically stays in sync with source data.