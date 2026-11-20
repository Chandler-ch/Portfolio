<script setup lang="ts">
const props = defineProps<{
  path: string;
  height: number;
}>();
</script>
<template>
  <img :style="`height: ${props.height}vb`" :src="props.path" />
</template>
<style scoped></style>
