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

```js

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

`<span>Message: {{ msg }}</span>` **mustache**

`v-once` to only render once and not update on data change

`v-html` to render raw html

`v-bind` for HTML attributes

Using JS Expressions
```
{{ number + 1 }}

{{ ok ? 'YES' : 'NO' }}

{{ message.split('').reverse().join('') }}

<div v-bind:id="'list-' + id"></div>
```

Only **one single expression** works. The following DOESN'T
```
<!-- this is a statement, not an expression: -->
{{ var a = 1 }}

<!-- flow control won't work either, use ternary expressions -->
{{ if (ok) { return message } }}
```

### Directives

**Directives** are special attributes with the `v-` prefix and are expected to be a **single JavaScript expression**

Some directives can take an **argument**, denoted by a colon after the directive name.
- `<a v-bind:href="url"> ... </a>`
- `<a v-on:click="doSomething"> ... </a>`

**Dynamic Arguments**: it is also possible to use a JavaScript expression in a
directive argument by wrapping it with square brackets:
- `<a v-bind:[attributeName]="url"> ... </a>`

Can also use dynamic arguments to bind a handler to a dynamic event name:
`<a v-on:[eventName]="doSomething"> ... </a>`
- When `eventName` is `focus`, it's equivalent to `v-on:focus`

**Modifiers** are special postfixes denoted by a dot, which indicate that a
directive should be bound in some special way. 

In this example, `.prevent` tells `v-on` directive to call
`event.preventDefault()` on the triggered event 
- `<form v-on:submit.prevent="onSubmit"> ... </form>`

### Shorthands

`v-bind` Shorthand
- full syntax `<a v-bind:href="url"> ... </a>`
- shorthand `<a :href="url"> ... </a>`
- shorthand with dynamic argument `<a :[key]="url"> ... </a>`

`v-on` Shorthand
- full syntax `<a v-on:click="doSomething"> ... </a>`
- shorthand `<a @click="doSomething"> ... </a>`
- shorthand with dynamic argument `<a @[event]="doSomething"> ... </a>`

## Computed Properties and Watchers

Use a `computed` property. E.g. `{{ reversedMessage }}` with
```js
var vm = new Vue({
  el: '#example',
	data: {
		message: 'Hello'
	},
	computed: {
		// a computed getter
		reversedMessage: function () {
			// `this` points to the vm instance
			return this.message.split('').reverse().join('')
		}
	}
})
```

**Computed Caching vs Methods**

We can achieve the same result by invoking a method in the expression:
```html
<p>Reversed message: "{{ reverseMessage() }}"</p>
```
```js
// in component
methods: {
  reverseMessage: function () {
    return this.message.split('').reverse().join('')
  }
}
```

However, **computed properties are cached based on their reactive
dependencies**. So using `Date.now()` in a computeed property will never update
because it's not a reactive dependency

**watch properties**: When you have some data that needs to change based on
some other data

Computed properties are by **default getter**-only. Use `set: function (...)` for setters

### Watchers

While computed properties are more appropriate in most cases, there are times
when a custom watcher is necessary. e.g. when you want to perform asynchronous
or expensive operations in response to changing data.


xxx
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
