<script setup lang="ts">
defineProps<{ projects: Record<string, any[]> }>()

</script>

<template>
  <div v-for="key in Object.keys(projects)" :key="key" class="ListBlog">
    <div class="mt-10 font-bold flex items-center">
      {{ key }}
      <div i-carbon-rocket class="ml-2" />
    </div>
    <div grid gap-4 grid-cols-2>
      <div
        v-for="item in projects[key]"
        :key="item.name"
        class="post mt-4 text-lg mb-1 cursor-pointer"
      >
        <div>
          <div>
            <div class="text-left mt-1">
              <a :href="item.link" target="_blank"> {{ item.name }} </a>
            </div>
            <div class="text-left desc text-sm opacity-50 font-normal">
              {{ item.desc }}
            </div>
          </div>
        </div>
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
