<template>
  <!-- The template section defines the structure of the component's HTML. -->
  <div>
    <h2>Reactivity Demo</h2>
    <!-- Displaying reactive data properties -->
    <p>Number (with ref): {{ numberRef }}</p>
    <p>Number (with reactive): {{ reactiveData.number }}</p>
    <p>String (with reactive): {{ reactiveData.string }}</p>
    <p>Array:</p>
    <ul>
      <!-- Looping through the array and displaying each item -->
      <li v-for="(item, index) in reactiveData.array" :key="index">{{ item }}</li>
    </ul>
    <p>Boolean (with ref): {{ booleanRef }}</p>
    <p>Boolean (with reactive): {{ reactiveData.boolean }}</p>
    <p>Object:</p>
    <ul>
      <!-- Looping through the object and displaying each key-value pair -->
      <li v-for="(value, key) in reactiveData.object" :key="key">{{ key }}: {{ value }}</li>
    </ul>
    <!-- Buttons for triggering different actions -->
    <button @click="incrementNumber">Increment Number (with ref)</button>
    <button @click="incrementReactiveNumber">Increment Number (with reactive)</button>
    <button @click="changeString">Change String</button>
    <button @click="addToEndOfArray">Add to Array</button>
    <button @click="toggleBoolean">Toggle Boolean (with ref)</button>
    <button @click="toggleReactiveBoolean">Toggle Boolean (with reactive)</button>
    <button @click="changeObject">Change Object</button>
  </div>
</template>

<script>
import { ref, reactive } from 'vue';

export default {
  name: 'ReactiveDemo',
  setup() {
    // Defining reactive data
    const numberRef = ref(0);
    const booleanRef = ref(true);
    const reactiveData = reactive({
      number: 0,
      string: 'Hello',
      array: ['apple', 'banana', 'cherry'],
      boolean: true,
      object: { name: 'John', age: 30 }
    });

    // Methods for manipulating reactive data
    const incrementNumber = () => {
      numberRef.value++;
      console.log('Number (with ref) is now:', numberRef.value);
    };

    const incrementReactiveNumber = () => {
      reactiveData.number++;
      console.log('Number (with reactive) is now:', reactiveData.number);
    };

    const changeString = () => {
      reactiveData.string = 'Hello Vue';
      console.log('String (with reactive) is now:', reactiveData.string);
    };

    const addToEndOfArray = () => {
      reactiveData.array.push('grape');
      console.log('Array (with reactive) is now:', reactiveData.array);
    };

    const toggleBoolean = () => {
      booleanRef.value = !booleanRef.value;
      console.log('Boolean (with ref) is now:', booleanRef.value);
    };

    const toggleReactiveBoolean = () => {
      reactiveData.boolean = !reactiveData.boolean;
      console.log('Boolean (with reactive) is now:', reactiveData.boolean);
    };

    const changeObject = () => {
      reactiveData.object.name = 'Alice';
      reactiveData.object.age = 25;
      console.log('Object (with reactive) is now:', reactiveData.object);
    };

    // Exporting reactive properties and methods to be used in the template
    return {
      numberRef,
      booleanRef,
      reactiveData,
      incrementNumber,
      incrementReactiveNumber,
      changeString,
      addToEndOfArray,
      toggleBoolean,
      toggleReactiveBoolean,
      changeObject
    };
  }
};
</script>

<style scoped>
h2 {
  color: blue;
}
</style>