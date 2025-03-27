<script>
    export default{
        data(){
            return{
                //datos alumnos
                alumnos:[
                    {nc: 12345, nombre: 'jorge', carrera:'ISC'},
                    {nc: 12345, nombre: 'luis', carrera:'ISC'},
                    {nc: 12345, nombre: 'Hernandez', carrera:'ISC'},
                    {nc: 12345, nombre: 'Hernandez', carrera:'ISC'},
                    {nc: 12345, nombre: 'Hernandez', carrera:'ISC'},
                    {nc: 12345, nombre: 'Hernandez', carrera:'ISC'},
                    {nc: 12345, nombre: 'Hernandez', carrera:'ISC'},
                    {nc: 12345, nombre: 'Hernandez', carrera:'ISC'}

                    //id, nombre completo, lo que les gusta en otro componente
                ]
            }
        }
    }
</script>
<template>
    <div class="container">
        <h3 class="mt-4" >Lista de alumnos</h3>
        <ul>
            <li v-for="alumno in alumnos" :key="alumno.nc">
                <strong>{{ alumno.nombre }} </strong> - 
                <strong>{{ alumno.carrera }} </strong>
            </li>
        </ul>
    </div>
 
</template> 
<style>
    h3{
        
        color: white;
        background-color: rgb(148, 185, 233);
        border-radius: 15px;
        padding: 10px;
        text-align: center;

    }
    ul{
        color: brown;
        list-style-type: none;
        padding: 8%

    }
    li{
        color: blue;
        background-color: black;
        border-radius: 15px;
        padding: 10px;
        margin: 10px;
        text-align: center;

    }
</style>