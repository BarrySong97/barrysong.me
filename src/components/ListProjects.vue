<script setup lang="ts">
</script>

<template>
  <div class="ListBlog">
    <div class="mt-10 font-bold flex items-center">
      Dev Efficiency
      <div i-carbon-rocket class="ml-2" />
    </div>
    <div grid gap-4 grid-cols-2>
      <div
        v-for="item in 6"
        :key="item"
        class="post mt-4 text-lg mb-1 cursor-pointer"
      >
        <div>
          <div>
            <div class="text-left mt-1">
              <a href="/"> Knife4j2TSApi </a>
            </div>
            <div class="text-left desc text-sm opacity-50 font-normal">
              Lorem ipsum dolor sit amet consectetur adipisicing elit.
              Laudantium inventore consequatur
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
