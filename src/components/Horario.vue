<template>
<div class="container">
  <h3>Horario de clases de Sistemas</h3>
  <table class="table">
  <thead>
    <tr>
      <th scope="col">Hora</th>
      <th scope="col">Lunes</th>
      <th scope="col">Martes</th>
      <th scope="col">Miercoles</th>
      <th scope="col">Jueves</th>
      <th scope="col">Viernes</th>
     
    </tr>
  </thead>
  <tbody>
    <tr v-for="(h,index) in horario" key="index">
      <td>
        {{ h.hora }}
      </td>
      <td>{{ h.lunes }}</td>
      <td>{{ h.Martes }}</td>
      <td>{{ h.miercoles }}</td>
      <td>{{ h.jueves }}</td>
      <td>{{ h.viernes }}</td>
      

    </tr>
  </tbody>
  
</table>
</div>
</template>

<script setup>
import { ref } from 'vue';

const horario = ref ([
  {hora:'7:00-9:00', lunes:'Ia',Martes:'Agil',miercoles:'web',jueves:'ia',viernes:'desarrollo movil'},
  {hora:'9:00-11:00', lunes:'Ia',Martes:'Agil',miercoles:'web',jueves:'ia',viernes:'desarrollo movil'},
  {hora:'7:00-9:00', lunes:'Libre',Martes:'Agil',miercoles:'web',jueves:'ia',viernes:'desarrollo movil'},
  {hora:'7:00-9:00', lunes:'Ia',Martes:'Agil',miercoles:'web',jueves:'ia',viernes:'desarrollo movil'},
  {hora:'7:00-9:00', lunes:'Ia',Martes:'Agil',miercoles:'web',jueves:'ia',viernes:'desarrollo movil'}

])
</script>