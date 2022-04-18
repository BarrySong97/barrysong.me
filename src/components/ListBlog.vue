<script setup lang="ts">
import { useRouter } from 'vue-router'

const router = useRouter()
const routes = router
  .getRoutes()
  .filter(i => i.path.startsWith('/posts'))
  .filter(v => v.name)
  .filter(v => v.name !== 'posts')
console.log(routes)

function onClickTitle(path: string) {
  router.push(path)
}
</script>

<template>
  <div class="ListBlog">
    <div v-for="item in routes" :key="item.name" class="post" mt-4>
      <div
        class="title"
        text-lg
        mb-1
        cursor-pointer
        @click="onClickTitle(item.path)"
      >
        {{ item.name }}
      </div>
      <div time opacity-50 text-sm mt-1>
        Feb 19 · 1min
      </div>
      <div>
        Lorem ipsum dolor sit amet consectetur, adipisicing elit. Temporibus
        autem.
      </div>
    </div>
  </div>
</template>

<style scoped>
.ListBlog {
  margin-bottom: 1.5rem;
}

.title {
  font-family: Montserrat, sans-serif;
  text-decoration: none;
  color: #d23669;
  font-size: 1.4rem;
}
</style>
