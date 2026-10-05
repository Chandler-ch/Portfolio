<script setup lang="ts">
const props = defineProps<{
  path: string;
}>();
</script>
<template>
  <div>{{ props.path }}</div>
  <img class="picture" :src="props.path" />
</template>
<style scoped>
.picture {
  border-radius: 50%;
  border: black 3px solid;
  height: 40vb;
  width: auto;
}
</style>
