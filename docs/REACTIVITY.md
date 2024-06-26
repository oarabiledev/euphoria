# ```Implementing Reactivity```

To implement reactivity the following functions are provided :

- createSignal
- createState
- useState

## ```Industry's Obsession With Signals```

Signals provide some form of reactivity atleast when done well.

To create one :

```javascript
let isQuicheEater = createSignal(false);
```

The function takes a parameter as a default value, and returns the following methods :

- value
- subscribe
- unsubscribe

The `value` method is a setter and getter,
when used as a setter and a subscriber has been hoisted the function in the subscriber gets called and the new value is passed in it.

The subscribe basically subscribes to changes.

The unsubscribe function is used to clear out the subscriber, so when changes happen the subscriber function will not get called.

```javascript

let isQuicheEater = createSignal(false);

function quicheEaterTest(name){
    if (name.toLowerCase() === 'theo') isQuicheEater.value = true;
    // We even strictly checking, no mistakes
}

isQuicheEater.subscribe((val)=>{
    alert('he definitly a quiche dude')
})
quicheEaterTest('tHeo');
```

## ```Inspiration From React Query```

Firstly lets talk about the difference between createState and useState.

`createState` returns an object and its methods linked, these methods are :

- setState
- getState
- subscribe

The `setState` method allows you to define a new varaible for that function, and `getState` retrieves the value.

`useState` is a direct copy of React's useState Hook, it returns an array of function that you can apply destructuring to, to implement a reactivity model.
