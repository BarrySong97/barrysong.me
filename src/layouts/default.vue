<script setup lang="ts">
import { ref, watch } from 'vue'
import { useRoute, useRouter } from 'vue-router'
import { useScroll } from '@vueuse/core'
const getFrontmatter = (route: any) => {
  return (route.meta as any).frontmatter
}
const el = ref<HTMLElement | null>(null)
const { y } = useScroll(el)

const route = useRoute()
const isShowTopInfo = ref(true)
watch(
  () => route.name,
  (newName) => {
    const arr = ['about', 'index', 'projects']
    if (arr.includes(newName as string))
      isShowTopInfo.value = true
    else isShowTopInfo.value = false
  },
)

const darkMode = ref(false)
function switchDarkMode() {
  darkMode.value = !darkMode.value
}
</script>

<template>
  <main ref="el" class="px-4 py-2 text-center text-gray-700 dark:text-gray-200">
    <div class="layout">
      <Header />

      <AuthorInfo v-if="isShowTopInfo" />
      <div class="main">
        <Nav v-if="isShowTopInfo" />
        <RouterView />

        <div v-if="!isShowTopInfo" class="text-left">
          <a
            href="/"
            class="
              font-mono
              no-underline
              opacity-50
              hover:opacity-75
              border-b-1 border-b-indigo
            "
          >cd..</a>
        </div>

        <a v-if="y > 200" href="#top" class="back-to-top-link" aria-label="Scroll to Top">BackToTop</a>
      </div>
    </div>
  </main>
</template>
<style scoped>
.blogNameContainer {
  margin-bottom: 32px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.back-to-top-link {
  position: fixed;
  bottom: 4rem;
  right: 5rem;
  color: #a0ada0;
  font-size: 0.8em;
  width: 16rem;
}
.darkModeSwitch {
  font-size: 2rem;
}
.blogName {
  font-family: Montserrat, sans-serif;
  font-weight: 900;
  font-size: 2rem;
  box-shadow: none;
  text-decoration: none;
  color: #222;
}
.layout {
  margin: 0 auto;
  padding: 2.625rem 1.3125rem;
  max-width: 42rem;
  font-family: "Merriweather", "Georgia", serif;
}
.avatar {
  border-radius: 50px;
  height: 3.5rem;
}
.authorName {
  text-align: left;
  font-weight: bold;
  color: hotpink;
}

.authorInfo {
  display: flex;
  align-items: center;
  /* justify-content: center; */
}

.authorDetail {
  height: 3.5rem;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  margin-left: 16px;
}

.main {
  margin-top: 2rem;
}
</style>
<route lang="yaml">
meta:
  layout: home
</route>
