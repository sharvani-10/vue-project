<template>
    <form @submit = "submitForm">
      <div>
        <pre>
          <!-- template to script and script to template  - two way data binding-->
           <!-- entered input will appear on ui with 2 spaces-->
          {{ JSON.stringify(formValues,null,2) }}
        </pre>
        <label for = "name">Name</label>
        <input type = "text" id="name" v-model = "formValues.name"/>
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
      <label>skill set </label>
      <input type = "checkbox" id = "html" value = "html" v-model = "formValues.skillSet"/>
      <label for = "html">HTML</label>
      <input type = "checkbox" id = "css" value = "css" v-model = "formValues.skillSet"/>
      <label for = "css">css</label>
      <input type = "checkbox" id = "js" value = "js" v-model = "formValues.skillSet"/>
      <label for = "js">js</label>
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
                yearsOfExperience:''
              }
            }
          },
  
          methods:{
            submitForm(event){
              event.peventDefault()
              console.log('Form values', this.formValues)
            //   it will console all the values in console after submission
            }
          }
         }
      </script>
      
      <style>
      
      </style>