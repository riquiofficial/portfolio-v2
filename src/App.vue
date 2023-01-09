<script setup lang="ts">
import { ref } from 'vue'
import { mdiMenu, mdiMoonWaningCrescent, mdiWhiteBalanceSunny  } from '@mdi/js'


const elevation = ref(2)
const theme = ref('dark')
const isDarkTheme = () => theme.value === "light"

const raiseElevation = () => {
  elevation.value = 5
}

const reduceElevation = () => {
  elevation.value = 1
}

const changeTheme = () => {
  theme.value = isDarkTheme() ? 'dark' : 'light'
  console.log(theme.value)
}

</script>

<template>
  <v-app :theme=theme>
    <v-app-bar @mouseleave="reduceElevation" @mouseenter="raiseElevation" :elevation="elevation" title="Navigation" >
      <v-app-bar-nav-icon ><v-icon :icon="mdiMenu" /></v-app-bar-nav-icon>

      <v-btn @click="changeTheme()">
        <v-icon :icon="isDarkTheme() ? mdiMoonWaningCrescent : mdiWhiteBalanceSunny" />
      </v-btn>
      
      
    </v-app-bar>
    <v-main>
      <v-container>Content area</v-container>
      

    </v-main>
  </v-app>
</template>
