<div align="center">
<a href="https://github.com/Mahboub99/every-day-Learning" rel="noopener">
  
  ![every day learning](https://user-images.githubusercontent.com/43186742/106606559-f23db080-656a-11eb-8728-d5231dfcec62.png)


</div>

<h3 align="center">every day learning</h3>

<div align="center">
  
  [![GitHub contributors](https://img.shields.io/github/contributors/Mahboub99/every-day-Learning)](https://github.com/Mahboub99/every-day-Learning/contributors)
  [![GitHub issues](https://img.shields.io/github/issues/Mahboub99/every-day-Learning)](https://github.com/Mahboub99/every-day-Learning/issues)
  [![GitHub forks](https://img.shields.io/github/forks/Mahboub99/every-day-Learning)](https://github.com/Mahboub99/every-day-Learning/network)
  [![GitHub stars](https://img.shields.io/github/stars/Mahboub99/every-day-Learning)](https://github.com/Mahboub99/every-day-Learning/stargazers)
  [![GitHub license](https://img.shields.io/github/license/Mahboub99/every-day-Learning)](https://github.com/Mahboub99/every-day-Learning/blob/master/LICENSE)
  <img src="https://img.shields.io/github/languages/count/Mahboub99/every-day-Learning" />
  <img src="https://img.shields.io/github/languages/top/Mahboub99/every-day-Learning" />
  <img src="https://img.shields.io/github/languages/code-size/Mahboub99/every-day-Learning" />
  <img src="https://img.shields.io/github/issues-pr-raw/Mahboub99/every-day-Learning" />

</div>

## About
> every-day-learning is a collection of questions and answers that i write down through my journey in learning ,here you might find various questions in front end , problem solving and programming languages



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

| methods                                                                                   | computed                                                   |
|:-----------------------------------------------------------------------------------------:| :---------------------------------------------------------:| 
| To call a function when an event happen in the DOM                                        | You need to compose new data from existing data sources    |     
| To call a function from the computed or watchers when something happens in your component.| You need to reference a value directly in your template    |
| You need to pass parameters                                                               | You call the same function more than once in your template |



### what is the diffrence between Primitive and Reverance value in js?
> [Complete answer](https://www.javascripttutorial.net/javascript-primitive-vs-reference-values).


>In JavaScript, a variable may store two types of values: primitive and reference.
JavaScript provides six primitive types as `undefined`, `null`, `boolean`, `number`, `string`, and `symbol` , and a reference type `object`(also `array`).
The size of a primitive value is fixed, therefore, JavaScript stores the primitive value on the `stack`.
On the other hand, the size of a reference value is dynamic so JavaScript stores the reference value on the `heap`.


### How to count the number of inversions in an array ?

> we can do it in `O(n^2)` the brute force solution 

> ```
initialize arr to [1,2,4,3,5,6]
initialize i to 0
initialize inversions to 0
while i is less than length of arr
  initialize j to i+1
  
  while j is less than length of arr
    if arr[i] is greater than arr[j]
      then increment inversions by 1
print out inversions
> ``` 
>or we can use merge sort in `O(nlog(n))` devide and conquer algorithm.
```
function countInversions(array) {
  if length of array is equal to 1
    return array
  midPoint = length of array \ 2
  firstHalf, inversions1 = mergeSort(first half of the array)
  secondHalf, inversions2 = mergeSort(second half of the array)
  initialize sortedArray to an empty array
  initialize i to 0
  initialize j to 0
  initialize inversions to 0
  while i < length of firstHalf and j < length of secondHalf
    if firstHalf[i] > secondHalf[j]
      append secondHalf[j] to sortedArray
      inversions = inversions + (midPoint - i)
    else
      append firstHalf[i] to sortedArray
  append the remaining elements of firstHalf to sortedArray
  append the remaining elements of secondHalf to sortedArray
  totalInversions = inversions1 + inversions2 + inversions
  return sortedArray, totalInversions
}
```
