<template>
  <div>
    <div class="header">
      <nav>导航栏</nav>
      <div class="menu">
        <NuxtLink class="item" to="/"><button>index Page</button></NuxtLink>
        <NuxtLink class="item" :to="`/detail`"><button>detail Page</button></NuxtLink>
        <NuxtLink class="item" :to="`/detail/${num}`">
          <button>detail/{{ num }} Page</button>
        </NuxtLink>
      </div>
    </div>
    <div style="background-color: skyblue; padding: 20px">
      <slot />
    </div>
  </div>
</template>

<script lang="ts" setup>
const num = ref(1); // 初始值为 1
onMounted(() => {
  num.value = Math.floor(Math.random() * 10) + 1; // 在客户端渲染时生成随机数
});

</script>

<style scoped>
.header {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: flex-start;
}

.header .menu {
  display: flex;
  justify-content: flex-start;
  padding: 20px 0;
}

.header .menu .item {
  margin-right: 10px;
}
</style>
