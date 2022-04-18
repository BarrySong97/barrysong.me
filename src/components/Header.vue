<template>
  <div class="blogNameContainer">
    <a id="top" class="blogName dark:text-white" href="/">overreacted</a>
    <div flex>
      <span style="font-size: 12px" self-end text-gray mr-2 cursor-pointer>Ctrl + K 搜索</span>
      <Action />
    </div>
  </div>
</template>
<style scoped>
.blogNameContainer {
  margin-bottom: 32px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.blogName {
  font-family: Montserrat, sans-serif;
  font-weight: 900;
  font-size: 2rem;
  box-shadow: none;
  text-decoration: none;
  color: rgb(255, 167, 196);
}
</style>
