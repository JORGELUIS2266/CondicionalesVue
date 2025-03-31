<script setup>
import Hijo1 from './Hijo1.vue';
import Hijo2 from './Hijo2.vue';

defineProps({
  nombre: String,
})
</script>

<template>
 <div class="container music-container">
    <h1 class="music-title">Música</h1>
    <div class="music-cards">
      <Hijo1 class="mt-4" tipo="Músicos con conocimiento de solfeo"
      imagen="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSHAJjyclvqAOGVpgmBAV5yiULeyxfsCtDMYQ&s"
      />
      <Hijo2 class="mt-4" tipo="Músicos autodidactas o intuitivos"
      imagen="https://blog.kiversal.com/wp-content/uploads/2020/06/Sonido.jpg"/>
    </div>
 </div>
</template>

<style scoped>
.music-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 2rem;
  background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
  min-height: 100vh;
}

.music-title {
  color: #2c3e50;
  text-align: center;
  margin-bottom: 2.5rem;
  font-size: 2.8rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 1px;
  position: relative;
  padding-bottom: 1rem;
}

.music-title::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 100px;
  height: 4px;
  background: #3498db;
  border-radius: 2px;
}

.music-cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 2.5rem;
  justify-content: center;
  padding: 1rem;
}

@media (max-width: 768px) {
  .music-cards {
    grid-template-columns: 1fr;
  }
  
  .music-title {
    font-size: 2.2rem;
  }
}

/* Efecto hover para las cards hijas */
.music-cards :deep(.music-card) {
  transition: all 0.3s ease;
}

.music-cards :deep(.music-card:hover) {
  transform: translateY(-5px);
  box-shadow: 0 10px 20px rgba(0,0,0,0.1);
}
</style>