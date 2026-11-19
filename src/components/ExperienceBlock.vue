<script setup lang="ts">
const props = defineProps<{
  content: string;
}>();
</script>
<template>
  <div class="block">
    <span class="text">{{ content }}</span>
  </div>
</template>
<style scoped>
.text {
  margin: 1vb;
}
.block {
  border: 2px black solid;
  border-radius: 16px;

  display: flex;
}
</style>
