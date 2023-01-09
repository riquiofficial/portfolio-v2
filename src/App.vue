<script setup lang="ts">
import { ref } from 'vue'

const elevation = ref(2)
const theme = ref('dark')


const raiseElevation = () => {
  elevation.value = 5
  console.log(elevation)
}

const reduceElevation = () => {
  elevation.value = 1
  console.log(elevation)
}

const changeTheme = () => {
  theme.value = theme.value === 'light' ? 'dark' : 'light'
}

</script>

<template>
  <v-app :theme=theme>
    <v-app-bar @mouseleave="reduceElevation" @mouseenter="raiseElevation" :elevation="elevation" title="Navigation" >
    <v-navigation-drawer>Menu stuff</v-navigation-drawer>

    <v-btn
        @click="changeTheme"
      >Toggle Theme</v-btn>
    
    </v-app-bar>

  </v-app>
</template>
