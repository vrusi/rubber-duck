<script setup lang="ts">
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
  <div id="paper">
    <div id="lines">
      <div class="line" v-for="line in [...Array(10).keys()]"></div>
    </div>

    <textarea
      id="prompt"
      :placeholder="getPlaceholder()"
      rows="9"
      cols="50"
      autofocus
    ></textarea>
  </div>
</template>

<style lang="scss">
@import "../assets/colours.scss";

#paper {
  display: grid;
  border-radius: 1rem;
  background-color: $colour-paper-light;
  box-shadow: 1.5rem 1.5rem $colour-shadow;
}

#lines {
  grid-column: 1;
  grid-row: 1;
}

.line {
  height: 2rem;
  border-bottom: 1px $colour-line-horizontal solid;
}

#prompt {
  grid-column: 1;
  grid-row: 1;
  word-wrap: break-word;
  resize: none;
  background-color: transparent;
  margin: 0 0 0 4rem;
  padding: 2rem 3rem 2rem 2rem;
  border: none;
  border-left: 2px $colour-line-vertical solid;
  font-size: 1.5rem;
  line-height: 2rem;
  color: $colour-prompt-light;
}

#prompt::placeholder {
  color: $placeholder-light;
}

#prompt:focus {
  outline: none;
}

@media screen and (max-width: 425px) {
  #prompt {
    margin: 0 0 0 1rem;
    line-height: 1.5rem;
    font-size: 1rem;
    padding: 1.5rem 1rem;
  }

  .line {
    height: 1.5rem;
  }
}

@media (prefers-color-scheme: dark) {
  #paper {
    background-color: $colour-paper-dark;
    box-shadow: 1.5rem 1.5rem $colour-shadow-dark;
  }

  .line {
    border-bottom: 1px $colour-line-horizontal-dark solid;
  }

  #prompt {
    border-left: 2px $colour-line-vertical-dark solid;
    color: $colour-prompt-dark;
  }

  #prompt::placeholder {
    color: $placeholder-dark;
  }
}
</style>
