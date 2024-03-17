<template>
    <div>
      <!-- Listening to events -->
      <div id="basic-event">
        <button @click="incrementCounter">Add 1</button>
        <p>The button above has been clicked {{ counter }} times</p>
      </div>
  
      <!-- Event handlers -->
      <div id="event-with-method">
        <button @click="greet">Greet</button>
      </div>
  
      <!-- Methods in inline handlers -->
      <div id="inline-handler">
        <button @click="say('hi')">Say hi</button>
        <button @click="say('what')">Say what</button>
      </div>
  
      <!-- Multiple event handlers -->
      <button @click="handleClick">Submit</button>
  
      <!-- Event modifiers -->
      <div>
        <a @click.stop="doThis">Stop event</a>
        <form @submit.prevent="onSubmit"></form>
        <div @click.capture="doThis">Track capture</div>
        <div @click.self="doThat">Track self</div>
      </div>
  
      <!-- Keyboard modifiers -->
      <input @keyup.enter="submit" />
  
      <!-- System modifiers -->
      <div @click.ctrl="doSomething">Do something</div>
  
      <!-- .exact modifier -->
      <button @click.ctrl="onClick">Ctrl + Click</button>
      <button @click.ctrl.exact="onCtrlClick">Ctrl + Click (Exact)</button>
      <button @click.exact="onClick">Click (Exact)</button>

  
      <!-- Display information -->
      <div>
        <p v-if="message">{{ message }}</p>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        counter: 0,
        name: 'Vue.js',
        message: ''
      }
    },
    methods: {
      // Event handlers
      incrementCounter() {
        this.counter++;
      },
      greet(event) {
        this.message = 'Hello, ' + this.name + '!';
        if (event) {
          this.message += ' Target Tag Name: ' + event.target.tagName;
        }
      },
  
      // Methods in inline handlers
      say(message) {
        this.message = message;
      },
  
      // Multiple event handlers
      handleClick(event) {
        this.one(event);
        this.two(event);
      },
      one(event) {
        this.message = 'First event handler logic executed';
      },
      two(event) {
        this.message = 'Second event handler logic executed';
      },
  
      // Event modifiers
      doThis() {
        this.message = 'Event modifier logic executed';
      },
      onSubmit() {
        this.message = 'Form submitted';
      },
      doThat() {
        this.message = 'Another event modifier logic executed';
      },
  
      // Keyboard modifiers
      submit() {
        this.message = 'Submitted by pressing Enter';
      },
      doSomething() {
        this.message = 'Something done with Ctrl + Click';
      },
  
      // .exact modifier
      onClick() {
        this.message = 'Ctrl + Click, regardless of other keys';
      },
      onCtrlClick() {
        this.message = 'Ctrl + Click, without other keys';
      }
    }
  }
  </script>