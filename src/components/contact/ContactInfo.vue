<script setup lang="ts">
const props = defineProps<{
  title: string;
  path?: string;
}>();
</script>
<template>
  <img :src="props.path" />
  <span>{{ props.title }}</span>
</template>
<style scoped></style>
