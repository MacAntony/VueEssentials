<template>
  <!-- Conditional rendering demonstration -->
  <div class="conditional-rendering-demo">
    <h2>Conditional Rendering Demo</h2>
    
    <!-- Using v-if -->
    <h3 v-if="awesome">Vue is awesome!</h3>
    <h3 v-else>Oh no 😢</h3>

    <!-- Using v-else-if -->
    <div v-if="randomNumber === 1">
      Rendered if randomNumber is 1
    </div>
    <div v-else-if="randomNumber === 2">
      Rendered if randomNumber is 2
    </div>
    <div v-else>
      Rendered if randomNumber is not 1 or 2
    </div>

    <!-- Using v-show -->
    <h3 v-show="showMessage">This message is shown using v-show</h3>

    <!-- Conditional rendering with v-if and v-for -->
    <ul v-if="showList">
      <li v-for="(item, index) in items" :key="index">{{ item }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'ConditionalRenderingDemo',
  data() {
    return {
      awesome: true,
      randomNumber: Math.floor(Math.random() * 3) + 1, // Random number between 1 and 3
      showMessage: true,
      showList: true,
      items: ['Item 1', 'Item 2', 'Item 3']
    };
  }
};
</script>

<style scoped>
/* Scoped styles for the component */
</style>
