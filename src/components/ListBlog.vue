<script setup lang="ts">
import { useRouter } from 'vue-router'

const router = useRouter()
const routes = router
  .getRoutes()
  .filter(i => i.path.startsWith('/posts'))
  .filter(v => v.name)
  .filter(v => v.name !== 'posts')

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
        {{ item.meta.frontmatter.title }}
      </div>
      <div time opacity-50 text-sm mt-1>
        <span text-base> {{ item.meta.frontmatter.date }}</span> · {{ item.meta.frontmatter.duration }}
      </div>
      <div text-slate-500>
        {{ item.meta.frontmatter.description }}
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
