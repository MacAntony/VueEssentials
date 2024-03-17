<template>
    <div>
      <h2>Demonstration of Template Refs</h2>
  
      <!-- Example using ref on an element -->
      <div ref="elementRef">
        <p>This is an element with ref</p>
      </div>
  
      <!-- Example using ref on a component -->
      <ChildComponent ref="childRef"></ChildComponent>
  
      <!-- Example using ref on v-for elements -->
      <ul>
        <li v-for="(item, index) in items" :key="index" :ref="setRef(index)">
          {{ item }}
        </li>
      </ul>
    </div>
  </template>
  
  <script setup>
  import ChildComponent from './ChildComponent.vue';
  import { ref, onMounted, watchEffect } from 'vue';
  
  // Declare refs
  const elementRef = ref(null);
  const childRef = ref(null);
  const itemRefs = ref([]);
  
  // Data for v-for
  const items = ref(['Item 1', 'Item 2', 'Item 3']);
  
  // Set ref function for v-for elements
  const setRef = (index) => (el) => {
    itemRefs.value[index] = el;
  };
  
  // Accessing refs after mount
  onMounted(() => {
    console.log("Element Ref:", elementRef.value);
    console.log("Child Component Ref:", childRef.value);
    console.log("Item Refs:", itemRefs.value);
  
    // Example of watching ref changes
    watchEffect(() => {
      if (elementRef.value) {
        // Do something with elementRef
        console.log("Element Ref changed:", elementRef.value);
      }
      if (childRef.value) {
        // Do something with childRef
        console.log("Child Component Ref changed:", childRef.value);
      }
      itemRefs.value.forEach((ref, index) => {
        if (ref) {
          // Do something with itemRefs
          console.log(`Item Ref ${index} changed:`, ref);
        }
      });
    });
  });
  </script>
  
  <!-- Child Component -->
  <ChildComponent />