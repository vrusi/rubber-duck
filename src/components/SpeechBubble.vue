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

/* taken and edited from https://codepen.io/kirstenallen/pen/MWwPYYm */
#speech-bubble {
  transform: translatey(0);
  animation: float 5s ease-in-out infinite;
  text-transform: uppercase;
  font-weight: bold;
  letter-spacing: 0.1rem;
  color: $colour-primary;
  background-color: $colour-bubble-background;
  padding: 3rem;
  border-radius: 1rem;
  box-shadow: 1.5rem 1.5rem $colour-shadow;
  font-size: 1.5rem;
}

#speech-bubble:after {
  transform: translatey(0);
  animation: float2 5s ease-in-out infinite;
  content: ".";
  font-weight: bold;
  text-shadow: 2rem 2rem $colour-shadow;
  text-align: right;
  font-size: 4rem;
  width: 4rem;
  height: 0.7rem;
  border-radius: 1rem;
  background-color: $colour-bubble-background;
  position: absolute;
  display: block;
  bottom: -2rem;
  left: 1rem;
  box-shadow: 1.5rem 1.5rem $colour-shadow;
  z-index: -2;
}

@keyframes float {
  0% {
    transform: translatey(0);
  }

  50% {
    transform: translatey(-1.3rem);
  }

  100% {
    transform: translatey(0);
  }
}

@keyframes float2 {
  0% {
    line-height: 2rem;
    transform: translatey(0);
  }

  55% {
    transform: translatey(-1.3rem);
  }

  60% {
    line-height: 0.5rem;
  }

  100% {
    line-height: 2rem;
    transform: translatey(0);
  }
}

@media screen and (max-width: 320px) {
  #speech-bubble:after {
    height: 0.6rem;
    width: 2rem;
    left: 0.2rem;
    font-size: 3rem;
    text-align: left;
  }
}
@media screen and (max-width: 768px) {
  #speech-bubble {
    font-size: 1rem;
    padding: 1rem;
  }
}

@media (prefers-color-scheme: dark) {
  #speech-bubble {
    color: $colour-shadow-dark;
    background-color: $colour-bubble-background-dark;
    box-shadow: 1.5rem 1.5rem $colour-shadow-dark;
  }
  #speech-bubble:after {
    -webkit-text-fill-color: $colour-bubble-background-dark;
    text-shadow: 22px 22px $colour-shadow-dark;
    background-color: $colour-bubble-background-dark;
    box-shadow: 1.5rem 1.5rem $colour-shadow-dark;
  }
}
</style>
