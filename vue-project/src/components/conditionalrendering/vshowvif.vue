<!-- conditional rendering -->
 <!-- v-if
  v-else
  v-else-if
  v-show -->

  <template>
    <!-- else-if condition -->
     <!-- if you have multiple conditions we use else if statement -->
  <h2 v-if="num ===0">The number is zero</h2>
  <h2 v-else-if="num < 0">The number is Negative</h2>
  <h2 v-else-if="num > 0">The number is Positive</h2>
  <h2 v-else>The number is not zero</h2>
  
  <template v-if = "display">
 <h2>hi</h2>
 <h2>hi</h2>
 <h2>hi</h2>
  </template>
  <h2 v-show = "showElement">using v-show</h2>
  <!-- it is associated to showelement if it is set to true it will show the element if it is set to false it will not show but it will present in dom, display is set to none-->
  <h2 v-if = "showElement">using v-show</h2>
  <!-- it is like v-show element only but here dom is not present  it will get unmounted from dom also-->
  <!--  -->
  </template>
  
  <script>
  export default{
        name:'App',
        data(){
          return{
            num:5,
            display:true,
            showElement:true
            // if we give another number  it wont show the statement of if "the number is zero"
          }
          },
        }
  </script>
  
  <style>
  </style>