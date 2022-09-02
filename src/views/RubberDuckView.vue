<script setup lang="ts">
import SpeechBubble from "../components/SpeechBubble.vue";
import Duck from "../components/Duck.vue";
import Prompt from "../components/Prompt.vue";
</script>

<template>
  <main>
    <div class="container">
      <h1>Let's debug!</h1>
      <SpeechBubble msg="What's your problem?" />
      <Duck />
      <Prompt />
    </div>
  </main>
</template>

<style lang="scss">
@import "../assets/colours.scss";

h1 {
  color: $color-d;
  margin: 2rem auto;
}
</style>
