<template>
  <div class="authorInfo">
    <img
      class="avatar"
      src="https://avatars.githubusercontent.com/u/23427423?s=400&u=ee287629b3cfc67873f9b324f09634a315bc8492&v=4"
    >
    <div class="authorDetail">
      <a class="authorName" href="">Barry Song</a>
      <div class="authorDescription">
        keep pushing(持续) is my way.
      </div>
    </div>
  </div>
</template>
<style scoped>
.avatar {
  border-radius: 50px;
  height: 4rem;
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
