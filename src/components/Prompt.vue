<script setup lang="ts">
import Button from "./Button.vue";

const placeholders = [
    "I'm implementing user registration and...",
    "My button component doesn't redirect. The way it works is...",
    "I am working on a component which... ",
]

function getPlaceholder() {
    return placeholders[Math.floor(Math.random()*placeholders.length)];
}
</script>

<template>
  <div id="wrapper">
    <div id="paper">
      <textarea
        :placeholder=getPlaceholder()
        id="text"
        name="text"
        rows="4"
        cols="50"
        style="word-wrap: break-word; resize: none"
      ></textarea>
    </div>
  </div>

  <Button />
  
</template>

<style></style>