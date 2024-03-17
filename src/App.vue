<script setup lang="ts">
import AppHeader from './components/AppHeader.vue'
import Greating from './components/Greating.vue'
import ReactiveDemo from './components/ReactiveDemo.vue'
import ComputedDemo from './components/ComputedDemo.vue';
import StyleBindingDemo from './components/StyleBindingDemo.vue';
import ConditionalRenderingDemo from './components/ConditionalRenderingDemo.vue';
import ListRenderingDemo from './components/ListRenderingDemo.vue';
import EventHandlingDemo from './components/EventHandlingDemo.vue';
import FormInputBindingDemo from './components/FormInputBindingDemo.vue';
import LifecycleHooksDemo from './components/LifecycleHooksDemo.vue';
import WatchersDemo from './components/WatchersDemo.vue';
import TemplateRefsDemo from './components/TemplateRefsDemo.vue';
import ComponentsBasicsDemo from './components/ComponentsBasicsDemo.vue';

</script>

<template>
  <main>
    <AppHeader/>
    <Greating />
    <ReactiveDemo />
    <ComputedDemo />
    <StyleBindingDemo />
    <ConditionalRenderingDemo />
    <ListRenderingDemo />
    <EventHandlingDemo />
    <FormInputBindingDemo />
    <LifecycleHooksDemo />
    <WatchersDemo />
    <TemplateRefsDemo />
    <ComponentsBasicsDemo/>
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
</style>
