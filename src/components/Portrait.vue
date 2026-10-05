<script setup lang="ts">
const props = defineProps<{
  path: string;
  height: number;
}>();
</script>
<template>
  <img :style="`height: ${props.height}vb`" class="picture" :src="props.path" />
</template>
<style scoped>
.picture {
  border-radius: 50%;
  border: black 3px solid;
}
</style>
