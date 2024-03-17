<template>
    <div>
      <!-- List rendering demonstration -->
      <h2>List Rendering Demo</h2>
      
      <!-- Rendering a list of items using v-for -->
      <h3>Items List:</h3>
      <ul>
        <li v-for="(item, index) in items" :key="item.id">
          <span v-if="editIndex !== index">{{ item.message }}</span>
          <input v-else v-model="editedMessage" @keyup.enter="saveEdit(index)" @keyup.escape="cancelEdit">
          <button @click="toggleEdit(index)">{{ editIndex === index ? 'Save' : 'Edit' }}</button>
          <button @click="removeItem(index)">Remove</button>
        </li>
      </ul>
      <div v-if="items.length === 0">No items available. Add some!</div>
  
      <!-- Rendering a list of objects with keys using v-for -->
      <h3>Object Properties:</h3>
      <ul>
        <li v-for="(value, key) in myObject" :key="key">
          {{ key }}: {{ value }}
        </li>
      </ul>
  
      <!-- Add new item form -->
      <h3>Add New Item:</h3>
      <form @submit.prevent="addItem">
        <input type="text" v-model="newItem" placeholder="Enter new item message">
        <button type="submit">Add</button>
      </form>
    </div>
  </template>
  
  <script>
  export default {
    name: 'ListRenderingDemo',
    data() {
      return {
        items: [
          { id: 1, message: 'Foo' },
          { id: 2, message: 'Bar' }
        ],
        myObject: {
          title: 'How to do lists in Vue',
          author: 'Anton Mac',
          publishedAt: '2024'
        },
        newItem: '',
        editIndex: null,
        editedMessage: ''
      };
    },
    methods: {
      toggleEdit(index) {
        if (this.editIndex === index) {
          this.saveEdit(index);
        } else {
          this.editIndex = index;
          this.editedMessage = this.items[index].message;
        }
      },
      saveEdit(index) {
        this.items[index].message = this.editedMessage;
        this.cancelEdit();
      },
      cancelEdit() {
        this.editIndex = null;
        this.editedMessage = '';
      },
      removeItem(index) {
        this.items.splice(index, 1);
      },
      addItem() {
        if (this.newItem.trim() !== '') {
          const newItem = {
            id: this.items.length + 1,
            message: this.newItem.trim()
          };
          this.items.push(newItem);
          this.newItem = ''; // Clear input field after adding
        }
      }
    }
  };
  </script>
  
  <style scoped>
  /* Scoped styles for the component */
  </style>