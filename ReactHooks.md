## React Hooks:

> Libray:

React Hooks are present in 'react libary' and they can be imported as:

```
import { useState, useEffect,  } from 'react'; 
```

Rules:
1. We can only use Hooks inside a function component and in exact same order
2. They cannot not inside a class Components, If statements or any other blocks



#### Use State (Similar to data in VUE)

1. Use state always returns a value of the state and setter for that state
2. We can pass on param as value:any|function|Object in use state to initialize a state's value or trigger the method everytime state value is changed

```
const [count, setCount] = useState(4)
// (or)
const [count, setCount] = useState({ count: 4, theme: 'blue' })
// (or)
const [count, setCount] = useState(someMethodName()) // This will call the method everyTime the stateValue is changed
// (or)
const [count, setCount] = useState(() => someMethodName()) // This will be called only once when a component is registered

```
3. State's setter param is considered value:any|function, which means using a function param we can mutate the value directly by accessing it's param. 

```
setCount( prevValue => prevValue+1)  //if the state is an non-object value, it is the best practise
// (or)

serCount( prevValue => {return { 'count': prevValue.count+1 } } ) // if the state is an object this should not be used, since the state is always overwritten, the keys missed in the return obj will be removed in the updated state

// (or)

serCount( prevValue => {return { ...prevValue, 'count': prevValue.count+1 } } ) // if the state is an object this is the best practise to be followed

```

#### Use Effect (Similar to watcher, mount, in VUE)

1. useEffect carries function and an array value as params

```
useEffect( () => { 
  console.log('This acts like watcher')
}, [stateOne] )
```

2. if the array params are empty it acts as mount, since no state is watched post mounted

```
useEffect( () => { 
  console.log('This acts like onMount')
}, [] )
```
3. However, eventListeners can be added to this and those can be triggered whenver a value is passed
4. A return method can be added to it and that will be triggered before the useEffect Actions are performed thus it can act as a cleanUp for that specific stateWatcher

```
const handleResize = () => {
  setWindowWidth(window.innerWidth)
}
useEffect( () => { 
  window.addEventListner( 'resize', handleResize )
  console.log('This acts like onMount')

  return () => {
    window.removeEventListner('resize') // ths
  }
}, [] )

```

#### Use Memo ( Similar to Computed in VUE )

1. This computes the value only once and saves it in a memory.

```
const doubleNumber = useMemo(() => {
  return 2*3; // some computation
},[number])
```

2. Always remember that computed uses extra memory so it is best practise to avoid using it unnecessaryly


#### Use Ref 

1. This returns the current value of the object
```
const renderCountRefObj = useRef(0)

useEffect( () => {
  renderCountRefObj.current = renderCountRefObj.current+1
} )
```

2. It can be used to refer a component by using ref keyword on HTML Element

```
const inputRef = useRef() // this denotes that inputRef is an ref Object

<input ref={inputRef} value=3 />  // This says that inputRef is denoting this element
```

#### Use Context

1. 