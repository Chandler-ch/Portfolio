<script setup lang="ts">
import { Suspense } from "vue";
import AnimatedText from "./components/AnimatedText.vue";
import Header from "./components/Header.vue";
import Title from "./components/Title.vue";
</script>

<template>
  <Header />
  <body>
    <div class="title side-container">
      <Title content="Amelia Chandler" />
      <AnimatedText
        beforeAnimation="21 year old ISFJ who likes to "
        :possibleEndings="['abc']"
      ></AnimatedText>
    </div>
  </body>
</template>

<style scoped>
.title {
  margin-left: 5vb;
}
.side-container {
  margin-top: 3vb;
  display: grid;
  align-items: row;
}
</style>

<!-- 'build Software',
          'learn Kotlin',
          'cook meals',
          'program Websites',
          'cut videos',
          'edit pictures in photoshop',
          'sort everything',
          'document modules', -->
