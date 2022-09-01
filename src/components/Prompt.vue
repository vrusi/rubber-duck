<script setup lang="ts">
import Button from "./Button.vue";</script>

<template>
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

  <Button msg="What am I doing wrong?" />
  
</template>

<style></style>