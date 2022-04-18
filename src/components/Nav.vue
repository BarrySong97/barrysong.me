<!--.vitepress/theme/MyLayout.vue-->
<script setup>
import { useRoute } from 'vue-router'
import { computed } from 'vue'
const route = useRoute()

</script>

<template>
  <div class="router" text-left>
    <router-link to="/" class="router-item dark:text-white" :class="{ 'active': route.name === 'index'}">
      Blogs
    </router-link>
    <router-link to="/projects" class="router-item dark:text-white" :class="{ 'active': route.name === 'projects'}">
      Projects
    </router-link>
    <router-link to="/about" class="router-item dark:text-white" :class="{ 'active': route.name === 'about'}">
      About
    </router-link>
  </div>
</template>

<style scoped>
.router {
  margin-bottom: 16px;
}
.router-item {
  margin-right: 1rem;
  text-decoration: none;
  color: #555;
  font-weight: 400;
  font-size: 1.5rem;
}

.router-item:hover {
  color: #000;
}

.active {
   color: #000;
   /* font-weight: 50; */
}
</style>
