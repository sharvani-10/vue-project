<!-- template block : for html-->
<template>
    <!-- this is a static data -->
    <div>hello welcome this is static data</div>
    <!-- but if we want dynamic data -->
     <!-- to get a dynamic data we have to get ffrom the data object -->
     <!-- <div>hi {{greet}} {{ name }}</div> ..error...-->
      <div>hi {{ name }}</div>
      <!-- third way of binding the data-by using directive with the data property -->
      <!-- the only drawback of using data is the total inner text will  be displayed -->
  <!-- <div v-text="channel"></div> -->
  <!-- if you give inner text it will get error -->
  <!-- <div v-text="channel">hello</div> -->
   <!-- if you want to give html tags -->
  <div v-html="channel"></div>
  <!-- for links -->
  <div v-html="hack"></div>
  <!-- for heading -->
  <h2 v-bind:id="headingId">Heading</h2>
  <!-- for disabled button -->
   <button v-bind:disabled="isDisabled">Bind</button>
   <!-- for style properties for static classes-->
    <h2 class = "underline">underlined text</h2>
    <!-- for style properties for dynamic classes-->
     <!-- if we want to change classes dynamically -->
    <h2 v-bind:class = "status">status</h2>
    <!-- if we have a succes we can set to status to success and if we have error we can set to danger -->
    <!-- we can have both static and dynamic classes -->
    <h2 class = "underline" v-bind:class = "status">status</h2>
    <h2 v-bind:class = "ispromoted && 'promoted'">promoted movie</h2>
    <h2 v-bind:class = "isSoldout ? 'sold-out':'new'">sold out movie</h2>
    <!-- arrays,arrays conditionals -->
    <h2 v-bind:class = "['new','promoted']">newly promoted movie</h2>
    <h2 v-bind:class = "[ispromoted && 'promoted',isSoldout ? 'sold-out':'new']">array conditional movie</h2>
    <!--  objects-->
    <h2 v-bind:class = "{
    promoted:ispromoted,
    new:!isSoldout,
    'sold-out':isSoldout}">object conditional rendering</h2>
  </template>
  
  <!-- script tag for logic -->
   <!-- data is function -->
   <script>
   export default{
    name:"App",
    data(){
      return{
        // this name is the dynamic data which we have to send to html
        greet:"hello",
        name:"sharvani",
        channel:'<b>stayconnect</b>',
        hack:`<a href= "#" onclick = "alert('you have been hacked')">prize</a>`,
        headingId:'heading',
        isDisabled:true,
        // if we select to false then it wont be disabled
        status:'danger',
        // we can set to succes the class will change dynamically
        ispromoted:true,
        // if ispromoted is set to true then it will change to italic and set to false it will be in normal position
        // we can set data property
        isSoldout:true
        // orange color will set if it is true and if it is set to false it will set to green
       
      };
    },
   };
  </script>
  
  <!-- this is for style proporities-->
   <style>
   .underline{
     text-decoration:underline;
   }
   .promoted{
    font-style:italic;
   }
   .new{
     color:green;
   }
   
   .sold-out{
     color:orange;
   }
  
  </style>
  
  <!-- v-text is rarely used -->