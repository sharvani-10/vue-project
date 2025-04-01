<template>
  <h2>Full name - {{ firstName }} {{ lastName }}</h2>
  <!-- we can have this in return -->
  <h2>computed Full name - {{ fullName }}</h2>
  <!-- we can have this in computed also it will compute first name and last name -->
  <button @click="changefullname">change fullname </button>
  <!-- getters and setters given to button -->
  <h2>
  Total - {{ items.reduce((total , curr) =>(total = total+ curr.price),0) }}
</h2>
<!-- you can add item also by that the price will be added -->
<button @click = "items.push({id:3,title:'keyboard',price:50})">add item</button>
<!-- this is computed total -->
<h2>
  computed total - {{ total }}
</h2>

<h2>Method total - {{ getTotal() }} </h2>

<input type = "text" v-model = "country"/>
<!-- the above statement is for console -->
 <!-- when you type in input type a letter  then it will call function how many times we write that many times it will call -->
<template v-for = "item in items" :key = "item.id">
<h2 v-if = "item.price >100">{{ item.title }} {{ item.price }}</h2>
</template>
<!-- the above statement is filter method  without comnputed properties-->

<h2 v-for = "item in expensiveItems" :key = "item.id">{{ item.title }} {{ item.price }}</h2>
<!-- computed property with v-for -->
</template>
    
    <script>
       export default {
        name: 'App',
        data(){
          return{
            firstName:'sharvani',
            lastName:'vanaparthi',
            items:[{
              id:1,
              title:'tv',price:100,
            },
            {
              id:2,
              title:'phone',price:300,
            },
          ]
          }
        },
        methods:{
              getTotal(){
                console.log('getTotal Method')
                return   this.items.reduce((total , curr) =>(total = total+ curr.price),0) 

              },
              changefullname(){
                this.fullName="hello world"
              }
        },
        computed:{
          fullName:{
            get() {
              return `${this.firstName} ${this.lastName}`
            },
            // it will recieve the values as arguments
            set(value) {
              const names = value.split('')
              this.firstName = names[0]
              this.lastName = names[1]
            }
          },
          // computed full name and last name(strings)
          // fullName(){
          //   return `${this.firstName} ${this.lastName}`
          // },
          // computed reduce property
          total(){
            console.log('total computed property')
            return   this.items.reduce((total , curr) =>(total = total+ curr.price),0) 
          },
          // computed filter property
          expensiveItems(){
            return this.items.filter(item => item.price >100)
          }
        }
       }
    </script>
    
    <style>
    
    </style>