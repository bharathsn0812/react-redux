# Setting Up and Using Redux Toolkit with React

## 1. Install Dependencies

```
npm install @reduxjs/toolkit react-redux
```

## 2. Create a Redux Store

Create a file named `store.js`:

```javascript
import { configureStore } from '@reduxjs/toolkit'

const store = configureStore({
  reducer: {}
})

export default store
```

## 3. Wrap Your React App with Redux Provider

In your main `index.js` or `App.js`:

```jsx
import { Provider } from 'react-redux'
import store from './store'

ReactDOM.render(
  <Provider store={store}>
    <App />
  </Provider>,
  document.getElementById('root')
)
```

## 4. Create a Slice

Create a file for your slice, e.g., `counterSlice.js`:

```javascript
import { createSlice } from '@reduxjs/toolkit'

const counterSlice = createSlice({
  name: 'counter',
  initialState: { value: 0 },
  reducers: {
    increment: state => { state.value += 1 },
    decrement: state => { state.value -= 1 }
  }
})

export const { increment, decrement } = counterSlice.actions
export default counterSlice.reducer
```

## 5. Add Slice Reducers to the Store

Update your `store.js`:

```javascript
import { configureStore } from '@reduxjs/toolkit'
import counterReducer from './counterSlice'

const store = configureStore({
  reducer: {
    counter: counterReducer
  }
})

export default store
```

## 6. Use Redux State and Actions in Components

In your React component:

```jsx
import React from 'react'
import { useSelector, useDispatch } from 'react-redux'
import { increment, decrement } from './counterSlice'

function Counter() {
  const count = useSelector(state => state.counter.value)
  const dispatch = useDispatch()

  return (
    <div>
      <button onClick={() => dispatch(decrement())}>-</button>
      <span>{count}</span>
      <button onClick={() => dispatch(increment())}>+</button>
    </div>
  )
}

export default Counter
```

This guide provides a basic setup for Redux Toolkit with React. For more advanced usage, refer to the official Redux Toolkit documentation.
