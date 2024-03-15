<template>
    <div>
      <h1>{{ greeting }}</h1>
      <p>{{ message }}</p>
      <button @click="changeMessage">Change Message</button>
    </div>
  </template>
  
  <script>
  export default {
    name: 'Greeting',
    data() {
      return {
        greeting: 'Hello, world!',
        message: 'This is an example of using the component in a Vue application.'
      };
    },
    methods: {
      changeMessage() {
        this.message = 'Message changed!';
      }
    }
  };
  </script>
  
  <style scoped>
  h1 {
    color: blue;
  }
  </style>
