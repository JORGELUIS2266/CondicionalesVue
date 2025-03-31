<script>
export default {
    data() {
        return {
            // Array de objetos con información de alumnos
            alumnos: [
                // Cada alumno tiene id, número de control, nombre completo, carrera y array de gustos
                { id: 1, nc: 12345, nombreCompleto: 'Jorge Luis Hernandez Matra ', carrera: 'ISC', gustos: ['Programación', 'Videojuegos', 'Música'] },
                { id: 2, nc: 12346, nombreCompleto: 'Roldan Uriel Arcadio Avila', carrera: 'ISC', gustos: ['sistemas', 'circuitos', 'musica'] },
                { id: 3, nc: 12347, nombreCompleto: 'Jenifer Hernández Sánchez', carrera: 'IC', gustos: ['Planos', 'Videojuegos', 'Música'] },
                { id: 4, nc: 12348, nombreCompleto: 'Ana Ramirez Ramírez', carrera: 'LA', gustos: ['Contabilidad', 'Lectura', 'Cocina'] },
                { id: 5, nc: 12349, nombreCompleto: 'Kevin Andrew Osorio Aparicio', carrera: 'ISC', gustos: ['Base de datos', 'Cine', 'Fotografía'] },
                { id: 6, nc: 12350, nombreCompleto: 'Nancy Osorio', carrera: 'ISC', gustos: ['Programación', 'Videojuegos', 'Música'] },
                { id: 7, nc: 12351, nombreCompleto: 'Pedro Garcia Garcia', carrera: 'ISC', gustos: ['Sistemas Operativos', 'Música', 'Deportes'] },
                { id: 8, nc: 12352, nombreCompleto: 'Blanca Estela Riveros', carrera: 'ISC', gustos: ['Programación', 'Videojuegos', 'Música'] }
            ]
        }
    }
}
</script>

<template>
    <!-- Contenedor principal que ocupa todo el ancho (container-fluid) -->
    <!-- mt-4: margen superior | px-lg-5: padding horizontal en pantallas grandes -->
    <div class="container-fluid mt-3 px-lg-5">
        <!-- Card principal con sombra ligera -->
        <div class="card shadow-sm">
            <!-- Cabecera de la card con gradiente CSS -->
            <div class="card-header bg-primary text-white" style="background: linear-gradient(135deg, #3498db, #2c3e50);">
                <!-- Título centrado con icono de personas -->
                <h3 class="mb-0 text-center"><i class="bi bi-people-fill me-2"></i>Lista de Alumnos</h3>
            </div>
            
            <!-- Cuerpo de la card con padding 4 -->
            <ul class="card-body p-4">
                <!-- Row con gap 4 entre columnas -->
                <div class="row g-4 ">
                    <!-- Columnas responsivas: 
                         - col-xxl-3: 4 columnas en pantallas extra grandes (>1400px)
                         - col-xl-4: 3 columnas en pantallas grandes (>1200px)
                         - col-lg-6: 2 columnas en pantallas medianas (>992px)
                         - col-md-6: 2 columnas en tablets (>768px) -->
                    <li class="col-xxl-3 col-xl-4 col-lg-6 col-md-6" v-for="alumno in alumnos" :key="alumno.id">
                        <!-- Card individual para cada alumno -->
                        <!-- h-100: altura completa | border-0: sin borde | shadow-sm: sombra pequeña -->
                        <!-- hover-effect: clase para efectos hover personalizados -->
                        <div class="card h-100 border-0 shadow-sm hover-effect">
                            <!-- Cabecera de card con fondo semi-transparente -->
                            <div class="card-header bg-light bg-opacity-50">
                                <!-- Nombre del alumno con texto truncado si es muy largo -->
                                <h5 class="card-title mb-0 text-truncat">{{ alumno.nombreCompleto }}</h5>
                            </div>
                            
                            <!-- Cuerpo de la card -->
                            <div class="card-body">
                                <!-- Contenedor flex en columna -->
                                <div class="d-flex flex-column">
                                    <!-- Número de control con badge -->
                                    <div class="mb-2">
                                        <strong class="badge bg-secondary me-1">No. Control</strong>
                                        <strong>{{ alumno.nc }}</strong>
                                    </div>
                                    
                                    <!-- Carrera con badge -->
                                    <div class="mb-3">
                                        <strong class="badge bg-info me-1">Carrera</strong>
                                        <strong>{{ alumno.carrera }}</strong>
                                    </div>
                                    
                                    <!-- Sección de intereses -->
                                    <div class="interests-section mt-auto">
                                        <!-- Título con icono de corazón -->
                                        <h6 class="text-muted mb-2"><i class="bi bi-heart-fill text-danger me-1"></i>Intereses</h6>
                                        <!-- Contenedor flex para los badges de intereses -->
                                        <div class="d-flex flex-wrap gap-2">
                                            <!-- Badge por cada interés -->
                                            <strong class="badge bg-light text-dark border" v-for="(gusto, index) in alumno.gustos" :key="index">
                                                {{ gusto }}
                                            </strong>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </li>
                </div>
            </ul>
        </div>
    </div>
</template>

<style scoped>
strong{
    background-color: aquamarine;
}
h5{
    background-color: cadetblue;
    color: black;
}

h6{
    color: black;
    background-color: aqua;
}
h3{
        
        color: white;
        background-color: rgb(148, 185, 233);
        border-radius: 15px;
        padding: 10px;
        text-align: center;

    }
    ul{
        color: rgb(51, 255, 0);
        background-color: blue;
        list-style-type: none;
        padding: 8%

    }
    li{
        color: rgb(46, 46, 230);
        background-color: rgb(2, 196, 255);
        border-radius: 15px;
        padding: 10px;
        margin: 10px;
        text-align: center;

    }
/* Efecto hover para las cards individuales */
.hover-effect {
    transition: all 0.3s ease; /* Transición suave de 0.3s */
    border: 1px solid rgba(0, 0, 0, 0.075); /* Borde muy sutil */
}

/* Efecto al hacer hover */
.hover-effect:hover {
    transform: translateY(-3px); /* Levanta ligeramente la card */
    box-shadow: 0 6px 15px rgba(0, 0, 0, 0.1) !important; /* Sombra más pronunciada */
    border-color: rgba(4, 152, 250, 0.3); /* Borde azul suave */
}

/* Estilo base para todas las cards */
.card {
    border-radius: 0.5rem; /* Bordes redondeados */
    overflow: hidden; /* Oculta contenido que sobresale */
}

/* Estilo para las cabeceras de las cards */
.card-header {
    border-bottom: none; /* Elimina borde inferior por defecto */
    padding: 1rem 1.25rem; /* Padding interno */
}


/* Estilo para los badges */
.badge {
    font-weight: 500; /* Grosor de fuente medio */
    padding: 0.35em 0.65em; /* Padding interno */
    font-size: 0.85em; /* Tamaño de fuente reducido */
}

/* Estilo para la sección de intereses */
.interests-section {
    margin-top: 1.25rem; /* Margen superior */
    padding-top: 1rem; /* Padding superior */
    border-top: 1px dashed #eee; /* Borde superior punteado */
}
</style>