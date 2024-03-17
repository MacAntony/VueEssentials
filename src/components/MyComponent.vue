<!-- MyComponent.vue -->

<template>
    <div :class="{ 'active': isActive, 'error': hasError }">
      MyComponent
    </div>
  </template>
  
  <script>
  export default {
    props: {
      isActive: {
        type: Boolean,
        default: false
      },
      hasError: {
        type: Boolean,
        default: false
      }
    }
  };
  </script>
  
  <style>
  .active {
    font-weight: bold;
  }
  .error {
    color: red;
  }
  </style>
  