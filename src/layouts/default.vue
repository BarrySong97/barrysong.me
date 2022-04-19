<script setup lang="ts">
import { computed, ref } from 'vue'
import { useRoute } from 'vue-router'
import { useScroll } from '@vueuse/core'
const getFrontmatter = (route: any) => {
  return (route.meta as any).frontmatter
}
const el = ref<HTMLElement | null>(null)
const { y } = useScroll(el)

const route = useRoute()
const isShowTopInfo = computed(() => {
  return ['about', 'index', 'projects'].includes(route.name as string)
})

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
        <h1
          v-if="!isShowTopInfo"
          class="text-left"
        >
          TestTtitle
        </h1>
        <div v-if="!isShowTopInfo" time opacity-50 text-sm text-left mt-1 mb-8>
          Feb 19 · 1min
        </div>
        <Nav v-if="isShowTopInfo" />
        <RouterView />

        <div
          v-if="!isShowTopInfo"
          class="text-left"
        >
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

        <a

          href="#top"
          class="back-to-top-link"
          aria-label="Scroll to Top"
        >BackToTop</a>
      </div>
    </div>
  </main>
</template>
<style scoped>
h1 {
  font-weight: 800;
  font-size: 2.25em;
  margin-top: 0;
  line-height: 1.1111111;
}
.blogNameContainer {
  margin-bottom: 32px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.back-to-top-link {
  position: fixed;
  bottom: 3rem;
  right: 2rem;
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
