<template>
  <div>
    <div class="header">
      <div class="user">
        <h2>nuxt3教学</h2>
        <img class="avatar" src="~/assets/user.png" alt="avatar" />
      </div>
      <nav>
        导航栏
        <img class="avatar" src="/logo.png" alt="avatar" />
      </nav>
      <div class="menu">
        <NuxtLink class="item" to="/">index Page</NuxtLink>
        <NuxtLink class="item" :to="`/detail`">detail Page</NuxtLink>
        <NuxtLink class="item" :to="`/detail/${num}`">detail/{{ num }} Page</NuxtLink>
      </div>
    </div>
    <div style="background-color: skyblue; padding: 15px">
      <slot />
    </div>
  </div>
</template>

<script lang="ts" setup>
const num = ref(1); // 初始值为 1

const handleClick = () => {
  num.value = Math.floor(Math.random() * 10) + 1; // 点击按钮时生成随机数
};
</script>

<style lang="scss" scoped>
.header {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: flex-start;
  border: 5px solid purple;
  margin-bottom: 20px;
  padding: 15px;

  .user,
  nav {
    display: flex;
    justify-content: flex-start;
    align-items: center;
  }

  .user {
    background-color: rgba(128, 0, 128, 0.8);
    width: 100%;
    padding: 20px 10px;

    .avatar {
      width: 50px;
      height: 50px;
      border: 1px solid rgb(0, 180, 0);
      border-radius: 50%;
      margin-left: 10px;
    }
  }

  nav {
    background-color: lightpink;
    border-top: 1px solid #ccc;
    width: 100%;
    padding: 20px 10px;

    .avatar {
      width: 50px;
      height: 50px;
      border: 1px solid rgb(0, 180, 0);
      border-radius: 50%;
      margin-left: 10px;
    }
  }

  .menu {
    background-color: lightgray;
    display: flex;
    justify-content: flex-start;
    border-top: 1px solid #ccc;
    width: 100%;
    border-bottom: 1px solid #ccc;
    padding: 20px 10px;
    .item {
      margin-right: 20px;
    }
  }
}
</style>
