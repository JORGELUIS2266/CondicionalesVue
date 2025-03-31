<script setup>
import { ref } from 'vue'

defineProps({
  tipo: String,
  imagen:String,
})


</script>

<template>
  <h2>musicos tecnicos</h2>
  <img v-if="imagen" :src="imagen" alt="Músico intuitivo" class="music-image w-50">
    
  
  <p>{{ tipo }}</p>
  
</template>

<style scoped>
</style>
