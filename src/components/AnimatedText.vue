<script setup lang="ts">
import { onMounted, ref, type Ref } from "vue";

const props = defineProps<{
  beforeAnimation: string;
  possibleEndings: string[];
}>();

const sleep = (ms: number) =>
  new Promise<void>((resolve) => setTimeout(resolve, ms));

const waitingTime = 200;

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

      displayText.value = await addCharSlowlyToString(
        currentLetter,
        displayText.value,
      );
    }
    await sleep(10 * waitingTime);
    // loop through letters function
    for (
      let letterIndex = displayText.value.length;
      letterIndex > 0;
      letterIndex--
    ) {
      displayText.value = await removeCharSlowlyFromString(displayText.value);
    }
  }
}
// composable -- gibt ein neues wort zurück durch kombi char & string -- ev slowly und sonst nicht
async function addCharSlowlyToString(character: string, word: string) {
  await sleep(waitingTime);
  return word + character;
}

async function removeCharSlowlyFromString(word: string) {
  await sleep(0.5 * waitingTime);
  return word.slice(0, -1);
}
</script>
<template>
  <div>
    <span class="subtitle">{{ beforeAnimation }}</span>
    <span class="subtitle animated">{{ displayText }}</span>
  </div>
</template>
<style scoped>
.subtitle {
  font-size: 2vw;
}
.animated {
  color: pink;
}
</style>
