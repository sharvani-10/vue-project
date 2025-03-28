<!-- conditional rendering -->
 <!-- v-if
  v-else
  v-else-if
  v-show -->

  <template>
    <!-- if-else condition -->
  <h2 v-if="num ===0">The number is zero</h2>
  <h2 v-else="num ===0">The number is not zero</h2>
  
  </template>
  
  <script>
  export default{
        name:'App',
        data(){
          return{
            num:0
            // if we give another number  it wont show the statement of if "the number is zero"
          }
          },
        }
  </script>
  
  <style>
  </style>