<template>
  <div>
    <pre>{{JSON.stringify(formValues)}}</pre>
  </div>
  <form action="" @submit.prevent="submitForm">
    <div>
      <label for="name"></label>
      <input type="text" id="name" v-model.trim.lazy="formValues.name"/>
    </div>

    <div>
      <label for="profile">profile</label>
      <textarea id="profile" v-model="formValues.profileSummary"></textarea>
    </div>
    <div>
      <label for="country">Country</label>
      <select id="country" v-model="formValues.country">
        <option value="">Select Country</option>
        <option value="Kenya">Kenya</option>
        <option value="India">India</option>
        <option value="Uk">Uk</option>
      </select>
    </div>
    <div>
      <label for="jobLocation">jobLocation</label>
      <select id="job=location" name="job=location" multiple v-model="formValues.jobLocation">
        
        <option value="Kenya">Kenya</option>
        <option value="India">India</option>
        <option value="Uk">Uk</option>
      </select>
    </div>
    <div>
      <label for="Skill Set"></label>
      <br/>
      <input type="checkbox" id="html" value="html" v-model="formValues.skillSet"/>
      <label for="html">HTML</label>
      <input type="checkbox" id="Css" value="Css" v-model="formValues.skillSet"/>
      <label for="Css">Css</label>
      <input type="checkbox" id="Javascript" value="Javascript" v-model="formValues.skillSet"/>
      <label for="Javascript">Javascript</label>
    </div>
    <div>
      <label for="years-of-experience">Years of experience</label>
      <br/>
      <input type="radio" id="0-2" value="0-2" v-model="formValues.yearsOfExperience"/>
      <label for="0-2">0-2</label>
      <input type="radio" id="2-5" value="2-5" v-model="formValues.yearsOfExperience"/>
      <hr/>
      <label for="2-5">2-5</label>
      <input type="radio" id="5-10" value="5-10" v-model="formValues.yearsOfExperience"/>
      <label for="5-10">5-10</label>
    </div>
    <div>
      <label for="age">Age</label>
      <input @keyup.enter=submitForm() type="number" id="age" v-model.number="formValues.age"/>
    </div>
    <!-- <div>
      <button type="submit">Submit</button>
    </div> -->
</form>
</template>

<script>

export default {
  name: 'App',
  
  data() {
    return {
     formValues: {
      name: '',
      profileSummary: '',
      country: '',
      jobLocation: [],
      skillSet: [],
      yearsOfExperience: "",
      age:''
     }
    }
  },
  methods: {
    submitForm() {
      console.log('form vlues', this.formValues)
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.underline {
  text-decoration: underline;
}
.danger{
  color: red;
}
.success {
  color: green;
}
.promoted {
  font-style:italic ;
}
.sold-out {
  color: red;
}
</style>
