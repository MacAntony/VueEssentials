<template>
  <div>
    <h1>Components Basics Demo</h1>

    <!-- Example of using a child component -->
    <ButtonCounter />

    <!-- Example of passing props to a child component -->
    <BlogPost :title="'My Journey with Vue'" />

    <!-- Example of listening to events from a child component -->
    <div :style="{ fontSize: postFontSize + 'em' }">
      <BlogPost
        v-for="post in posts"
        :key="post.id"
        :title="post.title"
        @enlarge-text="increaseFontSize"
      />
    </div>

    <!-- Example of using content distribution with slots -->
    <AlertBox>
      <p>Something bad happened.</p>
    </AlertBox>

    <!-- Example of using dynamic components -->
    <component :is="currentTabComponent"></component>
    <button @click="switchTab">Switch Tab</button>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'
import ButtonCounter from './ButtonCounter.vue'
import BlogPost from './BlogPost.vue'
import AlertBox from './AlertBox.vue'
import Tab1Component from './Tab1Component.vue'
import Tab2Component from './Tab2Component.vue'
import Tab3Component from './Tab3Component.vue'

const posts = ref([
  { id: 1, title: 'My Journey with Vue' },
  { id: 2, title: 'Blogging with Vue' },
  { id: 3, title: 'Why Vue is so fun' }
])

const postFontSize = ref(1)

const tabs = [Tab1Component, Tab2Component, Tab3Component]
let currentTabIndex = ref(0)

const switchTab = () => {
  currentTabIndex.value = (currentTabIndex.value + 1) % tabs.length
}

const currentTabComponent = computed(() => tabs[currentTabIndex.value])

const increaseFontSize = () => {
  postFontSize.value += 0.1
}
</script>
