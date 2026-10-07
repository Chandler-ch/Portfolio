<script setup lang="ts">
const props = defineProps<{}>();
</script>
<template>
  <div class="block">
    <span class="text">test</span>
  </div>
</template>
<style scoped>
.text {
  margin: 1vb;
}
.block {
  border: 2px black solid;
  border-radius: 10%;

  display: flex;
}
</style>
