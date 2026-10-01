<script setup lang="ts">
import { onMounted, ref, type Ref } from "vue";
import { useTimeout } from "@vueuse/core";

const props = defineProps<{
  beforeAnimation: string;
  possibleEndings: string[];
}>();

const sleep = (ms: number) =>
  new Promise<void>((resolve) => setTimeout(resolve, ms));

const displayText: Ref<string> = ref("");

onMounted(async () => await hurensohn());

async function hurensohn() {
  for (
    let wordIndex = 0;
    wordIndex < props.possibleEndings.length;
    wordIndex++
  ) {
    if (props.possibleEndings[wordIndex] == undefined) break;
    const currentWord: string = props.possibleEndings[wordIndex];

    for (let letterIndex = 0; letterIndex < currentWord.length; letterIndex++) {
      const currentLetter: string = currentWord[letterIndex];

      await addCharSlowlyToString(currentLetter, currentWord);
    }
  }
}
// composable -- gibt ein neues wort zurück durch kombi char & string -- ev slowly und sonst nicht
async function addCharSlowlyToString(character: string, word: string) {
  if (character.length !== 1) return;
  displayText.value = word + character;
  await sleep(1000);
  console.log(word + character);
}
</script>
<template>
  <div>
    <span class="title">{{ beforeAnimation }}</span>
    <span class="title">{{ displayText }}</span>
  </div>
</template>
<style scoped>
.title {
  font-size: 2vw;
}
</style>
