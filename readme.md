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

xxx

## The Vue Instance
## Template Syntax
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
