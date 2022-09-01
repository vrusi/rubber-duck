<script setup lang="ts">
import SpeechBubble from "../components/SpeechBubble.vue";
import Duck from "../components/Duck.vue";
</script>

<template>
  <main>
    <div class="rubber-duck" style="text-align: center">
      <h1>Let's debug!</h1>
      <SpeechBubble msg="What's your problem?" />
      <Duck />

      <div id="wrapper">
        <div id="paper">
          <textarea
            placeholder="I'm implementing user registration and..."
            id="text"
            name="text"
            rows="4"
            cols="50"
            style="word-wrap: break-word; resize: none"
          ></textarea>
        </div>
      </div>

      <button class="button-17" role="button">What am I doing wrong?</button>
    </div>
  </main>
</template>
