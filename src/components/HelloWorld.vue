<script setup>
import { ref } from 'vue'

const bienvenida = ref("Bienvenidos a la seccion de condicionales")
const nombre = ref("jorge Luis")
const apellidos = ref("Hernandez Matra")
 
// defineProps({
//   msg: String,
// })
</script>

<template>
  <div class="coontainer">
    <h2 class="text-center">{{bienvenida}}</h2>
    <div class="row">
      <div class="cold-md-6">
        <h6 class="">{{ nombre }}</h6>
        <h6>{{ apellidos }}</h6>
      </div>
    </div>
  </div>  
    
    
</template>

<style scoped>
</style>
