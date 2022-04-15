<script setup lang="ts">
import { ref } from 'vue'
import { useRouter } from 'vue-router'

const getFrontmatter = (route: any) => {
  return (route.meta as any).frontmatter
}

const router = useRouter()

console.log(router.getRoutes().filter(i => i.path.startsWith('/posts')))

const darkMode = ref(false)
function switchDarkMode() {
  darkMode.value = !darkMode.value
}
</script>

<template>
  <main class="px-4 py-10 text-center text-gray-700 dark:text-gray-200">
    <div class="layout">
      <div class="blogNameContainer">
        <a class="blogName dark:text-white" href="">overreacted</a>
        <div flex>
          <span style="font-size: 12px" self-end text-gray mr-2 cursor-pointer>Ctrl + K 搜索</span>
          <Footer />
        </div>
      </div>
      <div class="authorInfo">
        <img
          class="avatar"
          src="https://overreacted.io/static/profile-pic-c715447ce38098828758e525a1128b87.jpg"
        >
        <div class="authorDetail">
          <a class="authorName" href="">Barry Song</a>
          <div class="authorDescription">
            I explain with words and code
          </div>
        </div>
      </div>
      <div class="main">
        <Nav />
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
