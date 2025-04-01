<!-- List rendering -->
 <!-- v-directive -->
  <!-- Array of strings -->
  <!-- Array of objects -->
  <!-- Array of arrays-->
  <!-- block of html elements -->
  <!-- object key value pairs-->

  <template>
    <!-- without indexes -->
  <h2 v-for="name in names" :key = "name">{{ name }}</h2>
  <!-- with indexes -->
  <h2 v-for="(name,index) in names" :key = "name">{{index}} {{ name}}</h2>
  <!-- with full names - array of objects -->
  <h2 v-for="name in fulNames" :key = "name.first">{{ name.first }} {{ name.last }}</h2>
  <div v-for = "actor in actors":key = "actor.name">
    <h2>{{ actor.name }}</h2>
    <h3 v-for = "movie in actor.movies":key = "movie">{{ movie }}</h3>
  </div>
  <h2 v-for = "(value,key,index) in myInfo" :key = "value">{{ index }} {{ key }} {{ value }}</h2>
  <!-- we can use v-for or template for rendering -->
  <template v-for = "name in names" :key=" name">
    <h2>{{ name }}</h2>
    <hr/>
  </template>
  </template>
  
  <script>
  export default{
    name:'App',
    data(){
          return{
            // array of strings
            names:['shar','vani','sharvani'],
            // array of objects
            fulNames:[
              {first:'sharvani',last:'vanaparthi'},
              {first:'clark',last:'kent'},
              {first:'sharvani',last:'vanaparthi'}
            ],
            // array of arrays
             actors:[
              {
                name:'jjj',
                movies:['aa','aaa'],
              },
              {
                name:'jjj',
                movies:['aa','aaa'],
              },
             ],
             myInfo:{
                   name:'hello',
                   channel:'codeevloutionn',
                   course:'vue',
             }
          }
    },
  }
  
  </script>
  
  <style>
  
  </style>