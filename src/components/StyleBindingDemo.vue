<template>
  <div>
    <!-- Class Binding -->
    <div :class="{ 'active': isActive, 'error': hasError }">
      Class Binding Demo
    </div>

    <!-- Array Syntax -->
    <div :class="[activeClass, errorClass]">
      Array Syntax Demo
    </div>

    <!-- Component Usage -->
    <my-component :class="{ 'active': isActive, 'error': hasError }">
      Component Usage Demo
    </my-component>

    <!-- Style Binding -->
    <div :style="{ color: activeColor, fontSize: fontSize + 'px' }">
      Style Binding Demo
    </div>

    <!-- Object Syntax -->
    <div :style="styleObject">
      Object Syntax Demo
    </div>

    <!-- Array Syntax -->
    <div :style="[baseStyles, overridingStyles]">
      Array Syntax Demo
    </div>

    <!-- Automatic Prefixes -->
    <div :style="{ display: ['-webkit-box', '-ms-flexbox', 'flex'] }">
      Automatic Prefixes Demo
    </div>

    <!-- Multiple Values -->
    <div :style="{ display: ['-webkit-box', '-ms-flexbox', 'flex'] }">
      Multiple Values Demo
    </div>

    <!-- Computed Class Object -->
    <div :class="computedClassObject">
      Computed Class Object Demo
    </div>

    <!-- Toggle buttons for dynamic changes -->
    <div>
      <button @click="toggleActive">Toggle Active</button>
      <button @click="toggleError">Toggle Error</button>
      <button @click="increaseFontSize">Increase Font Size</button>
    </div>
  </div>
</template>

<script>
// Import MyComponent for demonstration
import MyComponent from './MyComponent.vue';

export default {
  components: {
    MyComponent
  },
  data() {
    return {
      isActive: false,
      hasError: false,
      activeClass: 'active',
      errorClass: 'error',
      activeColor: 'blue',
      fontSize: 16,
      styleObject: {
        color: 'red',
        fontSize: '13px'
      },
      baseStyles: {
        color: 'green',
        fontWeight: 'bold'
      },
      overridingStyles: {
        fontSize: '20px',
        fontStyle: 'italic'
      }
    };
  },
  
  methods: {
    toggleActive() {
      this.isActive = !this.isActive;
    },
    toggleError() {
      this.hasError = !this.hasError;
    },
    increaseFontSize() {
      this.fontSize += 2;
    }
  },
  
  computed: {
    // Example of computed property
    computedClassObject() {
      return {
        active: this.isActive && !this.hasError,
        'text-danger': this.hasError
      };
    }
  }
};
</script>

<style scoped>
/* Define styles for demonstration */
.active {
  font-weight: bold;
}
.error {
  color: red;
}
</style>