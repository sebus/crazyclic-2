<script setup>
// On importe l'objet numbersList depuis le fichier js
import { numbersList } from '../assets/data.js'

// Déclaration de l'evènement avec vérification
const emit = defineEmits({
  centimetre: (number) => {
    if (typeof number === 'number') {
      return true
    } else {
      return false
    }
  },
})
</script>

<template>
  <div>
    <button v-for="number in numbersList" :key="number" @click="$emit('centimetre', number)">
      {{ number }} km
    </button>
  </div>
</template>

<style scoped></style>
