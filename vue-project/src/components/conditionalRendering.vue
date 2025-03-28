<!-- conditional rendering -->

<template>
    <template v-for = "name in names" :key="name">
      <h2 v-if = "name === 'bruce'">{{ name }}</h2>
      <!-- if it is brucee then only name should be displayed at website -->
    </template>
  </template>
  
  <script>
  export default{
    name:'App',
    data(){
          return{
            names:['bruce','clark','diana'],
             }
          }
    }
  
  
  </script>
  
  <style>
  
  </style>