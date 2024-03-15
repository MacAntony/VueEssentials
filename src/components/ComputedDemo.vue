<template>
    <div>
      <h2>Computed Properties Demo</h2>
      <p>Number: {{ number }}</p>
      <p>Squared Number: {{ squaredNumber }}</p>
      <p>Reversed String: {{ reversedString }}</p>
      <p>Joined Array: {{ joinedArray }}</p>
      <p>UpperCase String: {{ upperCaseString }}</p>
      <p>Even Numbers: {{ evenNumbers }}</p>
    </div>
  </template>
  
  <script>
  import { ref, computed } from 'vue';
  
  export default {
    name: 'ComputedDemo',
    setup() {
      const number = ref(5);
      const string = ref('hello');
      const array = ref([1, 2, 3, 4, 5]);
  
      // Computed property to calculate the square of a number
      const squaredNumber = computed(() => number.value * number.value);
  
      // Computed property to reverse a string
      const reversedString = computed(() => string.value.split('').reverse().join(''));
  
      // Computed property to join elements of an array into a string
      const joinedArray = computed(() => array.value.join(', '));
  
      // Computed property to convert a string to uppercase
      const upperCaseString = computed(() => string.value.toUpperCase());
  
      // Computed property to filter even numbers from an array
      const evenNumbers = computed(() => array.value.filter(num => num % 2 === 0));
  
      return {
        number,
        squaredNumber,
        string,
        reversedString,
        array,
        joinedArray,
        upperCaseString,
        evenNumbers
      };
    }
  };
  </script>

<style scoped>
h2 {
  color: blue;
}
</style>