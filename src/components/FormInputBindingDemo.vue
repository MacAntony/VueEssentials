<template>
    <div>
      <h2>Form Input Binding Demo</h2>
  
      <!-- Text Input -->
      <label for="message">Enter Message:</label>
      <input type="text" id="message" v-model="message" placeholder="Type something..." />
      <p>Message: {{ message }}</p>
  
      <!-- Multiline Text Input -->
      <span>Multiline Message:</span>
      <p>{{ message }}</p>
      <br />
      <textarea v-model="message" placeholder="Enter multiple lines"></textarea>
  
      <!-- Checkbox -->
      <input type="checkbox" id="checkbox" v-model="isChecked" />
      <label for="checkbox">{{ isChecked }}</label>
  
      <!-- Multiple Checkbox -->
      <div id="v-model-multiple-checkboxes">
        <input type="checkbox" id="jack" value="Jack" v-model="checkedNames" />
        <label for="jack">Jack</label>
        <input type="checkbox" id="john" value="John" v-model="checkedNames" />
        <label for="john">John</label>
        <input type="checkbox" id="mike" value="Mike" v-model="checkedNames" />
        <label for="mike">Mike</label>
        <br />
        <span>Checked names: {{ checkedNames }}</span>
      </div>
  
      <!-- Radio Buttons -->
      <div id="v-model-radiobutton">
        <input type="radio" id="one" value="One" v-model="picked" />
        <label for="one">One</label>
        <br />
        <input type="radio" id="two" value="Two" v-model="picked" />
        <label for="two">Two</label>
        <br />
        <span>Selected: {{ picked }}</span>
      </div>
  
      <!-- Select Dropdown -->
      <div id="v-model-select" class="demo">
        <select v-model="selected">
          <option disabled value="">Choose one option</option>
          <option>A</option>
          <option>B</option>
          <option>C</option>
        </select>
        <span>Selected: {{ selected }}</span>
      </div>
  
      <!-- Dynamic Select Dropdown -->
      <div id="v-model-select-dynamic" class="demo">
        <select v-model="selectedDynamic">
          <option v-for="option in options" :value="option.value">
            {{ option.text }}
          </option>
        </select>
        <span>Selected: {{ selectedDynamic }}</span>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'FormInputBindingDemo',
    data() {
      return {
        message: '',
        isChecked: false,
        checkedNames: [],
        picked: '',
        selected: '',
        selectedDynamic: '',
        options: [
          { text: 'One', value: 'A' },
          { text: 'Two', value: 'B' },
          { text: 'Three', value: 'C' }
        ]
      };
    }
  };
  </script>
  
  <style scoped>
  /* Scoped styles for the component */
  </style>  