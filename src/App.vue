<script setup>
// Import des components
import partOne from './components/partOne.vue'
import partTwo from './components/partTwo.vue'
import partThree from './components/partThree.vue'

import { ref } from 'vue'

const result = ref('')
const changeWord = (word) => {
  // On vient traiter la chaine
  result.value = word.charAt(0).toUpperCase() + word.toLowerCase().slice(1)
}

const colorAleatoire = ref('')
const colorSuprise = (colorsList) => {
  colorAleatoire.value = colorsList[Math.floor(Math.random() * colorsList.length)]
}

const numberConvert = ref('')
const fnNumberConvert = (number) => {
  numberConvert.value = number * 100000
}
</script>

<template>
  <h1>Crazy clics v2</h1>
  <partOne @correctWord="changeWord" />
  <div>Résultat : {{ result }}</div>

  <partTwo @allColors="colorSuprise" />
  <div>Résultat : {{ colorAleatoire }}</div>

  <partThree @centimetre="fnNumberConvert" />
  <div>Résultat : {{ numberConvert }} cm</div>

  <div></div>
</template>

<style scoped></style>
