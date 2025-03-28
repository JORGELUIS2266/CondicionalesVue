<template>
    <div class="container">
      <h3>Horario de clases de Sistemas</h3>
      <table class="table text-center table-bordered">
        <thead>
          <tr>
            <th scope="col">Ncontrol</th>
            <th scope="col">Nombre</th>
            <th scope="col">Grado</th>
            <th scope="col">Periodo</th>
            
          </tr>
        </thead>
        <tbody>
          <tr v-for="(h, index) in nombre" :key="index">
            <td>{{ h.Ncontrol }}</td>
            <td>{{ h.nombre}}</td>
            <td>{{ h.Grado }}</td>
            <td>{{ h.Periodo }}</td>
            
          </tr>
        </tbody>
      </table>

      <table class="table textlcenter table-bordered">
        <thead>
          <tr>
            <th scope="col">Carrera</th>
            <th scope="col">Especialidad</th>
            <th scope="col">Creditos</th>
            <th scope="col">Plan de Estudiante</th>
            
          </tr>
        </thead>

        <tbody>
          <tr v-for="(h, index) in carrera" :key="index">
            <td>{{ h.carrera }}</td>
            <td>{{ h.Especialidad}}</td>
            <td>{{ h.Creditos }}</td>
            <td>{{ h.Estudios }}</td>
            
          </tr>
        </tbody>
      </table>
      
      <table class="table text-center table-bordered">
        <thead>
          <tr>
            <th scope="col">Materia</th>
            <th scope="col">Rep</th>
            <th scope="col">Cr</th>
            <th scope="col">Lunes</th>
            <th scope="col">Martes</th>
            <th scope="col">Miércoles</th>
            <th scope="col">Jueves</th>
            <th scope="col">Viernes</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(h, index) in horario" :key="index">
            <td>{{ h.materia }}</td>
            <td>{{ h.rep }}</td>
            <td>{{ h.cr }}</td>
            <td>{{ h.lunes }}</td>
            <td>{{ h.martes || '--' }}</td>
            <td>{{ h.miercoles }}</td>
            <td>{{ h.jueves }}</td>
            <td>{{ h.viernes }}</td>
          </tr>
        </tbody>
      </table>
      
    </div>
  </template>
  
  <script setup>
  import { h,ref } from 'vue';
  
  const carrera = ref([
    {carrera:'INGENIERIA EN SISTEMAS COMPUTACIONALES',Especialidad:'',Creditos:'33',Estudios:'ISIC-2010-224'}
  ])

  const nombre = ref([
    {Ncontrol:'22620235',nombre:'Jorge Luis Hernandez Matra',Grado:'6',Periodo:'ENE-JUN 25'}
  ])

  const horario = ref([
        {materia:'SCD1015 / 6BS / Lenguajes y autómatas 1,Profesor: Solano Hernandez Miguel Angel',rep:'N',cr:'5',lunes: '11:00-13:00/MAG5', martes: '', miercoles: '11:00-13:00 aula4 ', jueves: '', viernes: '12:00-13:00/RDS' },
        {materia:'SCD1021 / 6BS / Redes de computadoras, Sanchez Vazquez Lucia',rep:'N',cr:'5',lunes: '', martes: '13:00-15:00/RDS', miercoles: ' ', jueves: '13:00-15:00/LDS', viernes: '16:00-17:00/LDS' },
        {materia:'AEB1055 / 6BS / Programación web, Vazquez Martinez Josue Israel',rep:'N',cr:'5',lunes: '', martes: '17:00-19:00/ACS', miercoles: '', jueves: '17:00-19:00/ACS', viernes: '13:00-14:00/ACS' },
        {materia:'SCA1026 / 6BS / Taller de sistemas operativos, Cruz Perez Jorge',rep:'N',cr:'4',lunes: '13:00-15:00/LDS', martes: '', miercoles: '13:00-15:00/LDS', jueves: '', viernes: '' },
        {materia:'SCB1001 / 6BS / Administración de base de datos, Garcia Hernandez Hilario Vidal',rep:'N',cr:'5',lunes: '', martes: '15:00-17:00/MAG4', miercoles: '15:00-17:00/LDS', jueves: '', viernes: '14:00-15:00/LDS' },
        {materia:'SCC1014 / 6BS / Lenguajes de interfaz, Sanchez Vazquez Lucia',rep:'N',cr:'4',lunes: '', martes: '11:00-13:00/MAGNA 2', miercoles: '17:00-19:00/RDS ', jueves: '', viernes: '' },
        {materia:'SCD1011 /6BS / Ingeniería de software, Roman Cruz Jose Alfredo',rep:'N',cr:'5',lunes: '15:00-17:00/LDS', martes: '', miercoles: '', jueves: '15:00-17:00/LDS', viernes: '15:00-16:00/RDS' },
  
  
      ]);

  
  
  </script>
  
  <style scoped>
    .container {
    background-color: #f8f9fa;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  }

  h3 {
    text-align: center;
    color: #333;
    font-weight: bold;
  }

  .table {
    background-color: white;
    border-radius: 5px;
    overflow: hidden;
  }

  th {
    background-color: #007bff;
    color: white;
    text-transform: uppercase;
    padding: 12px;
  }

  td {
    padding: 10px;
  }

  tr:nth-child(even) {
    background-color: #f2f2f2;
  }

  tr:hover {
    background-color: #d1ecf1;
  }

  .table-bordered {
    border: 2px solid #007bff;
  }

  </style>
  