<template>
    <!-- <h2>{{ name }}</h2> -->
    <!-- if you write in above way it will cahnge -->
    <h2 v-once>{{ name }}</h2>
    <!-- if you write in once it will not change -->
  
    <button @click = "name = 'sharvani'">change name</button>
    <h2 v-pre>{{ name }}</h2>
    <!-- v-pre will not complile html element -->
     <!-- if you dont have any v-directives that html elements use pre tag it wont complie and makes the website performance faster -->
    <h2>{{ name }}</h2>
    <!-- without v-pre it will compile -->
  
  </template>
      
      <script>
         export default {
          name: 'App',
          data(){
            return{
               name:'sharvani vanaparthi'
            }
          }
         }
      </script>
      
      <style>
      
      </style>