<template>
    <div class="container">
        <div class="row mt-4">
            <div>
                <h4>Evento click</h4>
                <button @click="clic" class="btn btn-danger" type="button">Dale clic</button>
                <button @click="SoyBoton" class="btn btn-warning mx-2" type="button">Dale clic 2</button>
            </div>
            <div>
                <h4>Evento Change</h4>
                <label class="input-group-text" for="nombre">Ingresa tu nombre</label>
                <input class="form-control mt-2" type="text" id="nombre" @change="nombreE">
                <p>El nombre ingresado es: <strong>{{ nombre }}</strong></p>
            </div>

            <div>
                <h4>Evento lugar </h4>
                <label class="input-group-text" for="ciudad">Ingresa tu ciudad</label>
                <input class="form-control mt-2" type="text" id="ciudad" @change="ciudadC">
                <p>La ciudad ingresada es: <strong>{{ ciudad }}</strong></p>
            </div>

            <div>
                <h3>Evento de mouseenter y mouseleave </h3>
                <div class="text-center"
                style="color:#fff; width: 300px; height: 200px; 
                background-color: black; text-align: center;padding: 15px; 
                border-radius: 14px;"
                @mouseenter="mostrarMensaje" @mouseleave="ocultarMensaje">
                <p >pase el mouseenter</p>
                <p >{{ mensaje }}</p>

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
            ciudad:'',
            mensaje:'',
        };
    },
    methods: {
        clic() {
            alert("Gracias por darle clic");
        },
        SoyBoton() {
            alert("Soy un botón");
        },
        nombreE(event) {
            this.nombre = event.target.value;
        },
        ciudadC(event){
            this.ciudad = event.target.value;
        },
        mostrarMensaje(){
            this.mensaje="El mouse a dentro del Rectangulo"
        },
        ocultarMensaje(){
            this.mensaje="El mouse esta fuera del Rectangulo"
        }
    }
};
</script>

<style>
</style>
