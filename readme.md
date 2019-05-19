# Vue.JS Essentials

https://vuejs.org/v2/guide/

## Introduction

### Declarative Rendering

[:ship:](https://github.com/arafatm/learn_vue/commit/1568792a75319bac75195ca5003a50c13f98bd85)
Hello World
- `{{ message }}` to render bound data

[:ship:](https://github.com/arafatm/learn_vue/commit/e7c84d91f9f5898256fb7e9ed65300ef29744d48)
Dynamically bound title
- `<span v-bind:title="message">`
- The `v-bind` attribute you are seeing is called a **directive**.  Directives
  are prefixed with `v-` to indicate that they are special attributes

### Conditionals and Loops

[:ship: c9d4df0](https://github.com/arafatm/learn_vue/commit/c9d4df0)
toggle element presence 
- `v-if="seen"`
- in console `app3.seen = false` to hide the element

[:ship: 95fee57](https://github.com/arafatm/learn_vue/commit/95fee57)
loop through array with `v-for` 
- in console `app4.todos.push({ text: 'New item' })` to see live render

### Handling User Input

[:ship: fbd5143](https://github.com/arafatm/learn_vue/commit/fbd5143)
`v-on` directive to attach event listeners that invoke methods

[:ship: 5217973](https://github.com/arafatm/learn_vue/commit/5217973)
2-way binding with `v-model`

### Composing with Components

**Component** is an abstraction that allows us to build large-scale
applications composed of small, self-contained, and often reusable components.

[:ship: 3f790fd](https://github.com/arafatm/learn_vue/commit/3f790fd)
`component` example
- `prop` is used to bind the repeated component using `v-bind`

## The Vue Instance

### Data and Methods

When a Vue instance is created, it adds all the properties found in its data
object to Vue’s reactivity system. When the values of those properties change,
the view will “react” 

It should be noted that properties in data are only reactive if they existed
when the instance was created. 
- If you know you’ll need a property later, but it starts out empty or
  non-existent, you’ll need to set some initial value.

The only exception to this being the use of `Object.freeze()`, which prevents
existing properties from being changed, which also means the reactivity system
can’t track changes.

Vue instances expose a number of useful instance properties and methods. These
are prefixed with $ to differentiate them from user-defined properties.

e.g. `$data`, `$el`, `$watch`

```javascript

var data = { a: 1 }

var vm = new Vue({
  el: '#example',
  data: data
})

vm.$data === data // => true
vm.$el === document.getElementById('example') // => true

// $watch is an instance method
vm.$watch('a', function (newValue, oldValue) {
  // This callback will be called when `vm.a` changes
})
```

### Instance Lifecycle Hooks

e.g. `created`, `mounted`, `updated`, `destroyed`

```
new Vue({
  data: {
    a: 1
  },
  created: function () {
    // `this` points to the vm instance
    console.log('a is: ' + this.a)
  }
})
// => "a is: 1"
```

![Lifecycle Diagram](lifecycle.png)

## Template Syntax
xxx
## Computed Properties and Watchers
## Class and Style Bindings
## Conditional Rendering
## List Rendering
## Event Handling
## Form Input Bindings
## Components Basics
## Components In-Depth
## Component Registration
## Props
## Custom Events
## Slots
## Dynamic & Async Components
## Handling Edge Cases
## Transitions & Animation
## Enter/Leave & List Transitions
## State Transitions
## Reusability & Composition
## Mixins
## Custom Directives
## Render Functions & JSX
## Plugins
## Filters
## Tooling
## Single File Components
## Unit Testing
## TypeScript Support
## Production Deployment
## Scaling Up
## Routing
## State Management
## Server-Side Rendering
## Internals
## Reactivity in Depth 
