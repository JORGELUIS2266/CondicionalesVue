<script setup>
import { ref } from 'vue'
import Hijo1 from './Hijo1.vue';
import Hijo2 from './Hijo2.vue';

defineProps({
  nombre: String,
})

</script>

<template>
 <div class="container">
    <h1>Soy el componente Padre</h1>
  <Hijo1 class="mt-4" edad="20"/>
  <Hijo2 class="mt-4" edad="18"/>
 </div>
</template>

<style scoped>
</style>
