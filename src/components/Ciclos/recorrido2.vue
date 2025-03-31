<script>
export default {
    data() {
        return {
            alumnos: [
                { id: 1, nc: 12345, nombreCompleto: 'Jorge Pérez López', carrera: 'ISC', gustos: 'Programación, Videojuegos' },
                { id: 2, nc: 23456, nombreCompleto: 'Luis García Martínez', carrera: 'ISC', gustos: 'Inteligencia Artificial, Robótica' },
                { id: 3, nc: 34567, nombreCompleto: 'María Hernández Sánchez', carrera: 'ISC', gustos: 'Diseño UX/UI, Fotografía' },
                { id: 4, nc: 45678, nombreCompleto: 'Ana Rodríguez Díaz', carrera: 'ISC', gustos: 'Ciberseguridad, Ajedrez' },
                { id: 5, nc: 56789, nombreCompleto: 'Carlos Martínez Jiménez', carrera: 'ISC', gustos: 'Blockchain, Música' },
                { id: 6, nc: 67890, nombreCompleto: 'Sofía López Gómez', carrera: 'ISC', gustos: 'Data Science, Lectura' }
            ]
        }
    }
}
</script>

<template>
    <div class="container my-5">
        <div class="row mb-4">
            <div class="col-12">
                <h1 class="text-center mb-4 title-style">Lista de Alumnos</h1>
                <p class="lead text-center subtitle-style">Información académica y preferencias de nuestros estudiantes</p>
            </div>
        </div>

        <div class="row row-cols-1 row-cols-md-2 row-cols-lg-3 g-4">
            <div class="col" v-for="alumno in alumnos" :key="alumno.id">
                <div class="card h-100 shadow-sm alumno-card">
                    <div class="card-header bg-primary text-white">
                        <h5 class="card-title mb-0">{{ alumno.nombreCompleto }}</h5>
                    </div>
                    <div class="card-body">
                        <div class="mb-3">
                            <strong class="badge bg-secondary me-2">No. Control</strong>
                            <strong>{{ alumno.nc }}</strong>
                        </div>
                        <div class="mb-3">
                            <strong class="badge bg-info text-dark me-2">Carrera</strong>
                            <strong>{{ alumno.carrera }}</strong>
                        </div>
                        <div>
                            <h6 class="section-title">Intereses:</h6>
                            <p class="interests-text">{{ alumno.gustos }}</p>
                        </div>
                    </div>
                    <div class="card-footer bg-light">
                        <li class="text-muted">ID: {{ alumno.id }}</li>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
h3{
        
        color: white;
        background-color: rgb(148, 185, 233);
        border-radius: 15px;
        padding: 10px;
        text-align: center;

    }
    li{
        color: blue;
        background-color: black;
        border-radius: 15px;
        padding: 10px;
        margin: 10px;
        text-align: center;

    }
.title-style {
    color: #2c3e50;
    font-weight: 700;
    text-shadow: 1px 1px 2px rgba(0,0,0,0.1);
    padding-bottom: 10px;
    border-bottom: 3px solid #3498db;
    display: inline-block;
}

.subtitle-style {
    color: #7f8c8d;
    font-style: italic;
}

.alumno-card {
    border-radius: 10px;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    border: none;
}

.alumno-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 10px 20px rgba(0,0,0,0.1);
}

.card-header {
    border-top-left-radius: 10px !important;
    border-top-right-radius: 10px !important;
}

.section-title {
    color: #3498db;
    font-size: 1rem;
    margin-top: 1rem;
    border-bottom: 1px dashed #eee;
    padding-bottom: 0.5rem;
}

.interests-text {
    color: #555;
    font-style: italic;
    background-color: #f8f9fa;
    padding: 8px;
    border-radius: 5px;
}

.badge {
    font-weight: 500;
    padding: 5px 8px;
}

/* Responsive adjustments
@media (max-width: 768px) {
    .title-style {
        font-size: 1.8rem;
    }
} */
</style>