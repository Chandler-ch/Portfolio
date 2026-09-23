<script setup lang="ts">
import Header from "./components/Header.vue";
</script>

<template>
  <header class="site-header">
    <Header></Header>
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
</style>
