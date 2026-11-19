<script setup lang="ts">
import SubText from "./SubText.vue";

const props = defineProps<{
  title: string;
  content: string;
}>();
</script>
<template>
  <span class="title">{{ title }}</span>
  <div class="block">
    <SubText :content="content" size="small" class="text"></SubText>
  </div>
</template>
<style scoped>
.title {
  font-size: xx-large;
}
.text {
  margin: 1vb;
}
.block {
  border: 2px black solid;
  border-radius: 16px;

  display: flex;
}
</style>
