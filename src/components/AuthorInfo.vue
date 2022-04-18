<template>
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
</template>
<style scoped>
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
</style>
