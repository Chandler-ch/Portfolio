<script setup lang="ts">
import Picture from "./Picture.vue";

const props = defineProps<{
  path: string;
  height: number;
}>();
</script>
<template>
  <Picture class="picture" :path="props.path" :height="props.height" />
</template>
<style scoped>
.picture {
  border-radius: 50%;
  border: black 3px solid;
}
</style>
