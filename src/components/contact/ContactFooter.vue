<script setup lang="ts">
import ContactInfo from "./ContactInfo.vue";
</script>
<template>
  <div class="container grid-container">
    <ContactInfo title="LinkedIn" />
    <ContactInfo title="Mail" />
    <ContactInfo title="Github" />
  </div>
</template>
<style scoped>
.container {
  margin-top: 30vb;
  margin-left: calc(-50vw + 50%);
  margin-right: calc(-50vw + 50%);
  margin-bottom: calc(-50vw + 50%);
  border-top-left-radius: 20%;
  border-top-right-radius: 20%;
  height: 50vb;
  background-color: gray;
}
.grid-container {
  display: flex;
  justify-content: space-around;
}
</style>
