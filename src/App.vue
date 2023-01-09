<script setup lang="ts">
import { ref } from 'vue'

const elevation = ref(2)

const raiseElevation = () => {
  elevation.value = 5
  console.log(elevation)
}

const reduceElevation = () => {
  elevation.value = 1
  console.log(elevation)
}

</script>

<template>
  <v-app>
    <v-app-bar @mouseleave="reduceElevation" @mouseenter="raiseElevation" :elevation="elevation" title="Navigation" />
  </v-app>
</template>
