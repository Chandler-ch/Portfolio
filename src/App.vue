<script setup lang="ts">
import Header from "./components/Header.vue";
</script>

<template>
  <header class="site-header">
    <img class="header-image" src="./assets/dev-header2.jpeg" />
  </header>
  <body></body>
</template>

<style scoped>
.site-header {
  width: 100vw;
  height: 20vh;
  margin-left: calc(-50vw + 50%);
  margin-top: calc(-50vw + 50%);
  overflow: visible;
  position: relative;
}

.header-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: center;
}
</style>
