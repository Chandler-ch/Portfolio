<script setup lang="ts">
import SubText from "./SubText.vue";

const props = defineProps<{
  title: string;
  content: string;
}>();
</script>
<template>
  <SubText :content="title" size="medium"></SubText>
  <div class="block">
    <SubText :content="content" class="text"></SubText>
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
