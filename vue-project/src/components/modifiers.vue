<template>
    <form @submit = "submitForm">
  
      <!-- prevent default modifiers -->
      <!-- <form @submit.prevent = "submitForm">
    -->
      <div>
        <pre>
          <!-- template to script and script to template  - two way data binding-->
           <!-- entered input will appear on ui with 2 spaces-->
          {{ JSON.stringify(formValues,null,2) }}
        </pre>
        <label for = "name">Name</label>
        <!-- <input type = "text" id="name" v-model = "formValues.name"/> -->
        <!-- lazy loading will improve the performance after input typed when we go to next field the typed element  will show -->
        <!-- lady modifier will bind on the changed input -->
        <input type = "text" id="name" v-model.trim.lazy = "formValues.name"/>
      </div>
  
      <div>
        <label for = "profile">profile summary</label>
        <textarea id="profile" v-model="formValues.profileSummary"></textarea>
  
      </div>
      <div>
      <label for = "Country">Country</label>
      <select id = "country" v-model = "formValues.Country">
        <option value = ''>select a country</option>
        <option value = 'india'>india</option>
        <option value = 'singapore'>SINGAPORE</option>
        <option value = 'US'>US</option>
      </select>
    </div>
    <br/>
    <br/>
  
    <div>
      <label for = "joblocation">jobloaction</label>
      <select id = "jobloaction" multiple v-model = "formValues.Joblocation">
        <option value = ''>select a country</option>
        <option value = 'india'>india</option>
        <option value = 'singapore'>SINGAPORE</option>
        <option value = 'US'>US</option>
      </select>
    </div>
    <br/>
    <br/>
    <div>
      <input type = "checkbox" id="remotework" v-model = "formValues.remoteWork"/>
  <!-- it will return true or false -->
  <input type = "checkbox" id="remotework" v-model = "formValues.remoteWork" true-value = "yes" false-value = "no"/>
  
      <label for = "remoteWork">open to remote work</label>
    </div>
  
    <div>
      <label for = "skillset">skill set </label>
      <input type = "checkbox" id = "html" value = "html" v-model = "formValues.skillSet"/>
      <label for = "html">HTML</label>
      <input type = "checkbox" id = "css" value = "css" v-model = "formValues.skillSet"/>
      <label for = "css">css</label>
      <input type = "checkbox" id = "js" value = "js" v-model = "formValues.skillSet"/>
      <label for = "js">js</label>
    </div>
  <!-- modifiers -->
    <div>
      <label for = "age">age </label>
      <input type = "number" id = "age" v-model = "formValues.age"/>
      <!-- the above input if you type nu,ber lyk 25 it will be stored as sting -->
      <!-- <input type = "number" id = "age" v-model.number = "formValues.age"/> -->
       <!-- if you type .number it will store in numbers in database not in strings -->
       <!-- event key modifier -->
       <input @keyup.enter = "submitForm" type = "number" id = "age" v-model.number = "formValues.age"/>
  
       <!-- if you type age and enter your form will be submitted -->
    </div>
  
    <div>
      <button>Submit</button>
    </div>
    </form>
  </template>
      
      <script>
         export default {
          name: 'App',
          data(){
            // here we have to add the new data property
            return{
              formValues:{
                name:'',
                profileSummary: '',
                Country: '',
                Joblocation :[],
                // remoteWork:false
                // we can store yes or no in data base
                remoteWork :"no",
                skillSet: [],
                // we can have radio button in empty string also
                // yearsOfExperience:'',
                age:'null'
              }
            }
          },
  
          methods:{
            submitForm(event){
              event.peventDefault()
              console.log('Form values', this.formValues)
            }
            // here in prevent modifiers you can remove the event and go to template go to form -- add @submit.prevent
          }
         }
      </script>
      
      <style>
      
      </style>