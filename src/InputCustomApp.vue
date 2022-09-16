<template>
   <InputComponent v-model="name"/>
</template>
  
<script>
import InputComponent from './components/InputComponent.vue';

  export default {
    name: 'App',
    components: {
    InputComponent
},
    data() {
      return {
        name:'John'
      }
    },
   
    methods: {
      
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
  