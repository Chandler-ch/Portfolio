<script setup lang="ts">
import { onMounted, ref, type Ref } from "vue";
import SubText from "./SubText.vue";

const props = defineProps<{
  beforeAnimation: string;
  possibleEndings: string[];
}>();

const sleep = (ms: number) =>
  new Promise<void>((resolve) => setTimeout(resolve, ms));

const waitingTime = 150;

const displayText: Ref<string> = ref("");

onMounted(async () => {
  while (props.possibleEndings.length > 0) {
    await textAnimation();
  }
});

async function textAnimation() {
  for (
    let wordIndex = 0;
    wordIndex < props.possibleEndings.length;
    wordIndex++
  ) {
    const currentWord: string = props.possibleEndings[wordIndex];

    for (let letterIndex = 0; letterIndex < currentWord.length; letterIndex++) {
      const currentLetter: string = currentWord[letterIndex];

      displayText.value = await addCharSlowlyToString(
        currentLetter,
        displayText.value,
      );
    }
    await sleep(10 * waitingTime);
    for (
      let letterIndex = displayText.value.length;
      letterIndex > 0;
      letterIndex--
    ) {
      displayText.value = await removeCharSlowlyFromString(displayText.value);
    }
    await sleep(5 * waitingTime);
  }
}
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
    <SubText size="medium" :content="beforeAnimation + ' '"> </SubText>
    <SubText class="animated" size="medium" :content="displayText"> </SubText>
  </div>
</template>
<style scoped>
.subtitle {
  font-size: 2vw;
}
.animated {
  color: pink;
}
.animated::after {
  content: "|";
  animation: blink 1s step-end infinite;
}

@keyframes blink {
  0%,
  100% {
    opacity: 1;
  }
  50% {
    opacity: 0;
  }
}
</style>
