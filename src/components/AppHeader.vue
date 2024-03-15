<template>
    <header class="app-header">
      <h1>{{ title }}</h1>
      <nav>
        <ul>
          <li><router-link to="/">Home</router-link></li>
          <li><router-link to="/about">About</router-link></li>
          <li><router-link to="/contact">Contact</router-link></li>
        </ul>
      </nav>
    </header>
  </template>
  
  <script>
  export default {
    name: 'Header',
    data() {
      return {
        title: 'Vue Essentials App'
      };
    }
  };
  </script>
  
  <style scoped>
  .app-header {
    background-color: #41b883;
    color: white;
    padding: 20px;
  }
  
  .app-header h1 {
    margin: 0;
  }
  
  .app-header nav ul {
    list-style: none;
    padding: 0;
  }
  
  .app-header nav ul li {
    display: inline;
    margin-right: 10px;
  }
  
  .app-header nav ul li a {
    color: white;
    text-decoration: none;
  }
  </style>
  