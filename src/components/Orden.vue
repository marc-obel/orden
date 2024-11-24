<script setup lang="ts">
import { ref } from 'vue';
import { onKeyStroke } from '@vueuse/core';

const content = ref('');

onKeyStroke((event) => {
  if (event.key === 'Backspace') {
    content.value = content.value.slice(0, -1);
  } else if (event.key === 'Meta' || event.key === 'CapsLock') return
  else {
    content.value += event.key;
  }
});</script>

<template>
  <h1 class="rainbow">{{ content }}</h1>
</template>

<style scoped>
.rainbow {
  background-image: linear-gradient(to right,
      #d20f39, #fe640b, #df8e1d, #40a02b, #04a5e5, #ea76cb, #8839ef);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  font-optical-sizing: auto;
  font-style: normal;
  overflow-wrap: anywhere; /* Break words wherever needed */
}

</style>
