<!--.vitepress/theme/MyLayout.vue-->
<script setup>
</script>

<template>
  <div class="router" text-left>
    <router-link to="/" class="router-item dark:text-white">
      Blogs
    </router-link>
    <router-link to="/projects" class="router-item dark:text-white">
      Projects
    </router-link>
    <router-link to="/about" class="router-item dark:text-white">
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
</style>
