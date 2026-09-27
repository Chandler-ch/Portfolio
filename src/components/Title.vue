<script setup lang="ts">
defineProps<{
  content: string;
}>();
</script>
<template>
  <span class="title">{{ content }}</span>
</template>
<style scoped>
.title {
  font-size: 6vw;
}
</style>
