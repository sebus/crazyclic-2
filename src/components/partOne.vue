<script setup>
// On importe l'objet wordsList depuis le fichier js
import { wordsList } from '../assets/data.js'

// Déclaration de l'evènement avec vérification
const emit = defineEmits({
  correctWord: (word) => {
    if (typeof word === 'string') {
      return true
    } else {
      alert("Ce n'est pas une chaîne de caractère")
      return false
    }
  },
})
</script>

<template>
  <div>
    <button v-for="word in wordsList" :key="word" @click="$emit('correctWord', word)">
      {{ word }}
    </button>
  </div>
</template>

<style scoped></style>
