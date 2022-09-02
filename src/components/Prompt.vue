<script setup lang="ts">
import Button from "./Button.vue";

const placeholders = [
  "I'm implementing user registration and...",
  "My button component doesn't redirect. The way I wrote it is...",
  "I am working on a component which... ",
];

function getPlaceholder() {
  return placeholders[Math.floor(Math.random() * placeholders.length)];
}
</script>

<template>
  <div class="paper">
    <div class="lines">
        <div class="line" v-for="line in [...Array(11).keys()] "></div>
    </div>

    <textarea :placeholder="getPlaceholder()" rows="10" cols="50"></textarea>
  </div>
</template>

<style>

.lines {
  width: 100%;
  height: 100%;
  grid-column: 1;
  grid-row: 1;
}

.line {
  width: 100%;
  height: 2rem;
  border-bottom: 1px rgba(0, 100, 255, 0.3) solid;
}

.paper {
  display: grid;
  width: 60vw;
  border-radius: 11px;
  background-color: #f2f2f2;
  margin: 2rem auto;
}

.paper > textarea {
  word-wrap: break-word;
  resize: none;
  width: 54vw;
  height: 100%;
  background-color: transparent;
  margin: 0 0 0 4rem;
  border: none;
  border-left: 2px rgba(255, 0, 0, 0.3) solid;
  padding: 2rem;
  grid-column: 1;
  grid-row: 1;
  font-size: 1.5rem;
  line-height: 2rem;
}

.paper > textarea:focus {
    outline: none;
}

</style>
