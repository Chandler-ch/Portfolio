<script setup lang="ts">
import { onMounted, ref } from "vue";
const props = withDefaults(
  defineProps<{
    content: string;
    size?: "big" | "medium" | "small";
  }>(),
  {
    size: "small",
  },
);

const fontSize = ref(0);

function resolveSize(size: "big" | "medium" | "small") {
  switch (size) {
    case "big":
      return 6;
    case "medium":
      return 2;
    default:
      return 1.1;
  }
}

onMounted(() => {
  fontSize.value = resolveSize(props.size);
});
</script>
<template>
  <span :style="{ fontSize: fontSize + 'vw' }">{{ content }}</span>
</template>
<style scoped></style>
