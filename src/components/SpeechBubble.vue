<script setup lang="ts">
import { onMounted, onUnmounted, ref } from "vue";

const messages = [
  "What is your problem?",
  "Is there an easier way to do this?",
  "What does that suggest?",
  "Wait... What?",
  "Aah, I see... But why?",
  "I'm not sure I'm following...",
  "What do you mean?",
  "What is it supposed to be doing?",
  "What have you tried doing so far?",
  "How did you implement it?",
  "Can you explain it to me step by step?",
  "I'm 5 years old. I've no idea what that means.",
  "I really don't get it. Can you be more specific about that?",
  "What were you expecting would happen?",
  "How is that not what you expected to happen?",
  "Are you using a proper debugging tool or just printing 'here'?",
  "Can you split it in smaller bits?",
  "Are there any dependencies?",
  "Where is it being used?",
  "How is it being used?",
  "Did you build all of it yourself? Do you understand all parts of it?",
  "Do you really need it?",
  "What are you trying to achieve?",
];

function getMessage() {
  return messages[Math.floor(Math.random() * messages.length)];
}

const currentMessage = ref(getMessage());

let intervalId = 0;
onMounted(() => {
  intervalId = setInterval(() => {
    currentMessage.value = getMessage();
  }, 30000);
});

onUnmounted(() => clearInterval(intervalId));
</script>

<template>
  <div id="speech-bubble">{{ currentMessage }}</div>
</template>

<style lang="scss" scoped>
@import "../assets/colours.scss";

#speech-bubble {
  transform: translatey(0px);
  animation: float 5s ease-in-out infinite;
  text-align: center;
  text-transform: uppercase;
  font-weight: bold;
  letter-spacing: 3px;
  color: $colour-primary;
  background-color: $colour-bubble-background;
  padding: 50px;
  border-radius: 11px;
  position: relative;
  box-shadow: 20px 20px $colour-shadow;
  font-family: "Baloo 2", cursive;
  max-width: 60vw;
  font-size: 1.5rem;
}

#speech-bubble:after {
  transform: translatey(0px);
  animation: float2 5s ease-in-out infinite;
  content: ".";
  font-weight: bold;
  // -webkit-text-stroke: 0.5px $colour-green;
  -webkit-text-fill-color: $colour-bubble-background;
  // border: 1px solid $colour-green;
  text-shadow: 22px 22px $colour-shadow;
  text-align: right;
  font-size: 4rem;
  width: 55px;
  height: 11px;
  line-height: 30px;
  border-radius: 11px;
  background-color: $colour-bubble-background;
  position: absolute;
  display: block;
  bottom: -30px;
  left: 20px;
  box-shadow: 22px 22px $colour-shadow;
  z-index: -2;
}

@keyframes float {
  0% {
    transform: translatey(0px);
  }

  50% {
    transform: translatey(-20px);
  }

  100% {
    transform: translatey(0px);
  }
}

@keyframes float2 {
  0% {
    line-height: 30px;
    transform: translatey(0px);
  }

  55% {
    transform: translatey(-20px);
  }

  60% {
    line-height: 10px;
  }

  100% {
    line-height: 30px;
    transform: translatey(0px);
  }
}

@media screen and (max-width: 380px) {
  #speech-bubble {
    font-size: 1rem;
    padding: 1rem;
    margin-bottom: 3rem;
  }
}

@media screen and (min-width: 1024px) {
  #speech-bubble {
    max-width: 40vw;
  }
}

@media (prefers-color-scheme: dark) {
  #speech-bubble {
    color: $colour-shadow-dark;
    background-color: $colour-bubble-background-dark;
    box-shadow: 20px 20px $colour-shadow-dark;
  }
  #speech-bubble:after {
    -webkit-text-fill-color: $colour-bubble-background-dark;
    text-shadow: 22px 22px $colour-shadow-dark;
    background-color: $colour-bubble-background-dark;
    box-shadow: 22px 22px $colour-shadow-dark;
  }
}
</style>
