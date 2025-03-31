<template>
    <div class="container mt-5">
        <div class="card shadow p-4">
            <h2 class="text-center text-primary">Registro de Estudiante</h2>
            
            <div class="form-group mb-3">
                <label for="nombre" class="form-label">Nombre del estudiante</label>
                <input class="form-control" type="text" id="nombre" @change="actualizarNombre">
                <p class="mt-2">Nombre: <strong>{{ nombre }}</strong></p>
            </div>

            <div class="form-group mb-3">
                <label for="ncontrol" class="form-label">Número de control</label>
                <input class="form-control" type="text" id="ncontrol" @change="actualizarNControl">
                <p class="mt-2">Número de control: <strong>{{ ncontrol }}</strong></p>
            </div>

            <div class="form-group mb-4">
                <label for="carrera" class="form-label">Carrera</label>
                <input class="form-control" type="text" id="carrera" @change="actualizarCarrera">
                <p class="mt-2">Carrera: <strong>{{ carrera }}</strong></p>
            </div>

            <div class="text-center">
                <h3 class="text-success">Interacción con Imagen</h3>
                <div class="image-container"
                     @mouseenter="cambiarImagen" @mouseleave="restaurarImagen">
                    <p class="fw-bold">Pase el mouse por encima</p>
                    <p>{{ mensaje }}</p>
                    <img :src="imagenActual" alt="Imagen interactiva">
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            nombre: '',
            ncontrol: '',
            carrera: '',
            mensaje: '',
            imagenNormal: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSsL7qhMdNHJbZrRuQK8SIfKtq4pS9JkIFFbA&s',
            imagenHover: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRTs5TGV_yyIxc53dnYmRbujxP763vu_EVZYA&s',
            imagenActual: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRTs5TGV_yyIxc53dnYmRbujxP763vu_EVZYA&s'
        };
    },
    methods: {
        actualizarNombre(event) {
            this.nombre = event.target.value;
        },
        actualizarNControl(event) {
            this.ncontrol = event.target.value;
        },
        actualizarCarrera(event) {
            this.carrera = event.target.value;
        },
        cambiarImagen() {
            this.mensaje = "El mouse está dentro del rectángulo";
            this.imagenActual = this.imagenHover;
        },
        restaurarImagen() {
            this.mensaje = "El mouse ha salido del rectángulo";
            this.imagenActual = this.imagenNormal;
        }
    }
};
</script>

<style>
.container {
    max-width: 600px;
    margin: auto;
}

.card {
    border-radius: 15px;
    background: #f8f9fa;
}

.image-container {
    background-color: #198754;
    width: 300px;
    height: 200px;
    border-radius: 14px;
    color: white;
    padding: 15px;
    margin: auto;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    transition: background 0.3s;
}

.image-container img {
    width: 120px;
    height: 120px;
    margin-top: 10px;
    border-radius: 8px;
}
</style>
