<!-- binding styles -->
<template>
    <h2 v-bind:style="{
      color:highlightColor,
      'font-size':headerSize + 'px',
      // as it is a number it should be in px
      // not only you can have kebab case you can have camelCase
      // 'fontSize':headerSize + 'px'
      padding:'20px'
    }">Inline styles</h2>
    <!-- multiple inline styles with object -->
    <h2 v-bind:style="headerStyleobject">style object</h2>
    <!-- multiple styles with multiple objects -->
    <div v-bind:style="[baseStyleobject,successStyleobject]">Sucess style</div>
     </template>
    
  <script>
    export default{
      name:'App',
      data(){
        return{
          highlightColor:'orange',
          headerSize:50,
          // if you have multiple inline styles go with object styles
          headerStyleobject:{
            color:'orange',
            fontSize:'50px',
            padding:'20px'
          },
          baseStyleobject:{
            fontSize:'50px',
            padding:'20px'
          },
          successStyleobject:{
            color:'green',
            backgroundColor:'lightgreen',
            border:'1px solid green',
            padding:'20px',
          },
  
        }
      },
    }
    </script>
    
    <style>
    </style>