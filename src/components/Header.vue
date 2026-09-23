<script setup lang="ts"></script>
<template>
  <header class="container">
    <img class="dev-picture" src="./../assets/dev-header2.jpeg" />
  </header>
</template>
<style scoped>
.container {
  width: 100vw;
  height: 20vh;
  margin-left: calc(-50vw + 50%);
  margin-top: calc(-50vw + 50%);
  overflow: visible;
  position: relative;
}
.dev-picture {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: center;
}
</style>
