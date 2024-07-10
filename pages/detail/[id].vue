<template>
  <div class="details">
    <h2>detail/{{ $route.params.id }} Page内壳</h2>
    <h2>$route.params: {{ $route.params }}</h2>
  </div>
</template>

<style lang="scss" scoped>
.details {
  border: 2px solid darkgreen;
  padding: 15px;
  background-color: #ccc;
  color: $link-color;
}
</style>
