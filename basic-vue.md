
## Start Vue project with vue cli

$ `vue create project-name`

### manual selection 

Babel -> Linter -> Unit Testing

Version 3.x ->  Eslint + Prettier ->  Lint on save ->  Jest ->  config files -> N for future projects (or Y if you want to have the same settings in future projects) 

### how to run the project

$ `yarn serve`

## Code structure of a component

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

