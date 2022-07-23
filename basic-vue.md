
## Start Vue project with vue cli

#### To install vue cli:
```
npm i -g @vue/cli
# OR
yarn global add @vue/cli
```

#### To start the project

$ `vue create project-name`

### manual selection 

Babel -> Linter -> Unit Testing

Version 3.x ->  Eslint + Prettier ->  Lint on save ->  Jest ->  config files -> N for future projects (or Y if you want to have the same settings in future projects) 

#### we can choose other things if we want 
like: router and vuex 

### how to run the project

$ `cd project-name

$ `yarn serve`
or 
$ `npm run serve`

## General structure of a component

```vue.js
<template>
  <h1>Hello World</h1>
  <component-example />
  or 
  <component-example>Text</component-example>
 </template>
 
 <script>
 import ComponentExample from "@/components/ComponentExample.vue";
 
 export default{
    name: "component's name",
    components: {"ComponentExample"},
   
    data() {
      return {
        key: value,
       };
      },
     methods: {
      myFunction() {
        this.key = newValue
        },
       },
      };
      
    
 </script>
 
 <style scoped>
 </style>
 ```
 
 ## v-directives
 
 ### v-bind 
 v-bind allows to connect a data value to an html attribute like link to html `a` tag or to bind value to a key in list elements
 v-bind is so frequently used that it can be replaced by `:` sign 
 
 `<a v-bind:href="url"> {{ name }} </a>` can be replaced by `<a :href="url">{{ name }}</a>`
 `<li :key="menuItems[menuItem]">{{ menuItem }}</li>` is the same as `<li v-bind:key="menuItems[menuItem]">{{ menuItem }}</li>`
 
 ### v-for 
 v-for is used usually on `li` element to loop through the list of items.  
 
 ```vue.js
 <li v-for="menuItem in menuItems" :key="menuItem">{{ menuItem }}</li>
 ```
 
 The list of items we need to loop over is from `data` in `script`
 
 ### v-if/v-else-if/v-else 
 v-if/v-else-if/v-else  those are conditional statements, we use them in templates to display elements (or given templates) on some conditions
 
 ```vue.js
 <button v-if="isLoggedIn">Log out</button>
 <button v-else>Log in</button>
 ```
 ### v-on 
 v-on is for event handling, for example click, v-on can be replaced by `@` sign
 
 `<button v-on:click="handleClick">Log in</button>` is the same as `<button @click="handleClick">Log in</button>` 
 
 And then in `script` we need to create the handleClick function. For this purpose we cannont use fat arrow functions.
 
 ```vue.js 
 <script>
  export default {
    name: "component's name,
    methods: {
        handleClick() {}
      },
     };
</script>
```

## props
Props - those are properites that are registrated in a parent component and then passed onto a child component (or more children components) 
They work only one way - always from the parent to the child!

In a child component we add the name of the prop in `script` part:

```vue.js
<script>
export default {
  name: "Example Button Component",
  props: ["text"],
}
</script>
```

We also have to add the prop's name to the html tag in `template`. In this example the prop's name is text.

```vue.js
<temaplate>
  <button>{{ text }}</vu>
</template
```

Now, in the parent component we can use the child component and here we can pass the value of the prop. We can use it more than once and add another value to the button:
```vue.js
<template>
  <example-button-component text="My button" />
  <example-button-component text="Second button" />
</template>
```

## lifecycle hooks 
#### created() 
for api calls
