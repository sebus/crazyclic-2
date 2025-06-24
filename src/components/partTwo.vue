<script setup>
// On importe l'objet colorsList depuis le fichier js
import { colorsList } from '../assets/data.js'

// Déclaration de l'evènement avec vérification
const emit = defineEmits({
  allColors: (colorsList) => {
    if (typeof colorsList === 'object') {
      return true
    } else {
      return false
    }
  },
})
</script>

<template>
  <div><button @click="$emit('allColors', colorsList)">Couleur surprise !</button></div>
</template>

<style scoped></style>
