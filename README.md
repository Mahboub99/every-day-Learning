
### How can I export a directory structure in Windows?

>[Complete answer](https://superuser.com/questions/258287/how-can-i-export-a-directory-structure-in-windows).
``` shell
tree /f /a > tree.txt
```

### How to install vue CLI?
``` shell
npm install -g vue-cli
```

### How to create vue app?
```shell
vue create <project name>
```

### what is the difference betwen "data" and "props" in vue?
> [Complete answer](https://medium.com/javascript-in-plain-english/different-between-props-and-data-in-vue-components-d571cfa078e4).

>There’s a difference between props and data. Data is stored in the private memory of each component where we can store variables that we need. Props are passed in from the parent component to the child.

#### example passing data from parent to child as props:

child:
```vue
<template>
  <div class="hello">
   <p>{{msg}}</p>

  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

```

parent:

```vue
<template>
  <div id="app">
   
    <HelloWorld :msg="title"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  data(){
    return{
      title:"from app component"
      }
  },
  components: {
    HelloWorld
  }
}
</script>
```

using `:msg="title"` to pass "title" as data not `string` 

### what is the differance between `methods` and `computed` in vue ?
>[Complete answer](https://medium.com/notonlycss/the-difference-between-computed-and-methods-in-vue-js-9cb05c59ed98).

>In comparison, a method invocation will always run the function whenever a re-render happens but computed just calls whenever the data is updated.

| methods                                                                                    | computed|
|:------------------------------------------------------------------------------------------:| :------:| 
| .To call a function when an event happen in the DOM                                        |You need to compose new data from existing data sources
You need to reference a value directly in your template
You call the same function more than once in your template         |
  .To call a function from the computed or watchers when something happens in your component.  
  .You need to pass parameters
