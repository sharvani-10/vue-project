<!-- methods -->

<template>
    <!-- for mathematical expressions -->
     <h2>{{ 2+3+5 }}</h2>
     <h2>{{ 5+10+15 }}</h2>
     <!-- addition -->
     <h2>Add method - {{ add(10,3,15) }}</h2>
     <!-- multiplication -->
     <h2>Multiply method - {{ multiply(10) }}</h2>
     <!-- another way for multiplication -->
     <h2>Multiply method - {{ multiply(basevalue) }}</h2>
  </template>
  
  <script>
  export default{
    name:'App',
    data(){
          return{
            baseMultiplier:5,
            // we can multiply to base value also
            basevalue:2
          }
    },
      methods: {
      add(a,b,c){
         return a+b+c
      },
      multiply(num){
        return num*this.baseMultiplier
      }
    },
  
  }
          
    // the functions are associated with methods called objects
    
  
  </script>
  
  <style>
  
  </style>