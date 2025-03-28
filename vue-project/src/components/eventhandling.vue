<template>
    <h2>{{ name }}</h2>
    <!-- we can change the name by method -->
    <div>
      <button v-on:click = "changeName">Change name</button>
    </div>
    <div>
      <button v-on:click = "name = 'sharvani vanaparthi'">change name</button>
      <button v-on:mouseover = "name = 'sharvani vanaparthi'">change name on mouse over</button>
    </div>
    <h2>{{ count }}</h2>
    <div>
      <button v-on:click="count += 1">increment</button>
      <button v-on:click="count -= 1">decrement</button>
      <!-- we can also increemnet by using methods -->
      <button v-on:click="increment">increment</button>
      <button v-on:click="decrement">decrement</button>
      <!-- we can increment by 5 and decrement by 1 by passing arguments-->
      <button v-on:click="increment(1,$event)">increment 1</button>
      <button v-on:click="decrement(1)">decrement 1</button>
      <button v-on:click="increment(5)">increment 5</button>
      <button v-on:click="decrement(5)">decrement 5</button>
    
      <!-- short hand for button click  it works as expected-->
      <button @click="increment(1)">increment 1</button>
    </div>
    </template>
    
    <script>
       export default {
        name: 'App',
        data(){
          return{
            name:'sharvani',
            count:0
          }
        },
        methods: {
          // increment(){
          //   this.count += 1
          // },
          // decrement(){
          //   this.count -= 1
          // },
    
          // or we can pass by arguments also
          // increment(num){
          //   this.count += num
          // },
    
          // dollar event - with console - event object
          increment(num,event){
            this.count += num
            console.log('Event',event)
          },
          decrement(num){
            this.count -= num
          },
    
          // changename
          // changeName(){
          //   this.name = "man"
          // },
    
          // we can do with event object aslo - when you click on event object on change name it will console all the details
          changeName(event){
            this.name = "man"
            console.log('Event',event)
          },
        }
       }
    </script>
    
    <style>
    
    </style>