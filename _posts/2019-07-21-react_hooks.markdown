---
layout: post
title:      "react hooks"
date:       2019-07-22 00:52:54 +0000
permalink:  react_hooks
---


what are they and how do we use them?


* added via React 16.8
* allow use of state and other React features without writing a class
* allow splitting larger component into smaller functions based on related pieces

introduced to solve following issues in React:
* unable to attach reusable behavior to a component without having to restructure
* lack of organizing stateful logic -- allows room for error and inconsistencies
* unable to break down complex components to testable smaller components

new function `useState`:

```
import React, { useState } from 'react';

function Example() {
  // Declare a new state variable, which we'll call "count"
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```
[example from React documentation](https://reactjs.org/docs/hooks-overview.html)
