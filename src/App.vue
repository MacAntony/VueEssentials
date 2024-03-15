<script setup lang="ts">
import AppHeader from './components/AppHeader.vue'
import Greating from './components/Greating.vue'
import ReactiveDemo from './components/ReactiveDemo.vue'
import ComputedDemo from './components/ComputedDemo.vue';
</script>

<template>
  <header>
    <AppHeader/>
  </header>

  <main>
    <Greating />
    <ReactiveDemo />
    <ComputedDemo />
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>./components/ReactiveDemo.vue
