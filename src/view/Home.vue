<script setup lang="ts">
import AnimatedText from "@/components/AnimatedText.vue";
import Portrait from "@/components/Portrait.vue";
import Title from "@/components/Title.vue";
</script>

<template>
  <body>
    <div class="main-container">
      <div class="left-container">
        <Title content="Amelia Chandler" />
        <AnimatedText
          beforeAnimation="21 year old ISFJ who likes to"
          :possibleEndings="[
            'build Software',
            'learn Kotlin',
            'cook meals',
            'program Websites',
            'cut videos',
            'edit pictures in photoshop',
            'sort everything',
            'document modules',
          ]"
        ></AnimatedText>
      </div>
      <div class="right-container">
        <Portrait />
      </div>
    </div>
  </body>
</template>

<style scoped>
.main-container {
  display: flex;
  justify-content: space-between;
}
.left-container {
  margin-left: 5vb;
  margin-top: 3vb;
}
.right-container {
  margin-right: 10vb;
}
</style>
