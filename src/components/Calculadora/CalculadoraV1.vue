<script>
    export default{
        data() {
            return {
                numero1:0,
                numero2:0,
                Resultado:0,
            }
        },
        methods:{
            sumar(){
                this.Resultado = parseFloat(this.numero1)+ parseFloat(this.numero2)
            },
            resta(){
                this.Resultado = parseFloat(this.numero1)- parseFloat(this.numero2)
            },
            multiplicacion(){
                this.Resultado = parseFloat(this.numero1)* parseFloat(this.numero2)
            },
            division(){
                this.Resultado = parseFloat(this.numero1)/ parseFloat(this.numero2)
            }
            
        }
    }
</script>

<template>
    <div class="container mt-5">
        <div class="card shadow p-4">
            <h1>CalculadoraV1</h1>
            <h2 class="text-end">{{ Resultado }}</h2>

            <div class="mb-3">
                <label for="">Numero 1</label>
                <input type="number" class="form-control" v-model="numero1">
            </div>
            
            <div class="mb-3">
                <label for="">Numero 2</label>
                <input type="number" class="form-control" v-model="numero2">
            </div>

            <div class="d-flex justify-content-center gap-2">
                <button @click="sumar" class="btn btn-danger">Sumar</button>
                <button @click="resta" class="btn btn-warning">Resta</button>
                <button @click="multiplicacion" class="btn btn-primary">Multiplicacion</button>
                <button @click="division" class="btn btn-warning">Division</button>
            </div>

            <!-- <h2 class="text-center mt-4">Resultado:{{ Resultado }} </h2> -->
        </div>

    </div>
</template>
<style>
.text-end{
    background-color: rgb(44, 238, 238);
    border: 5px;
    border-color: black;
    border-bottom: 10px;
}
h2{
    border-radius: 12px;
    padding: 10px;
}

</style>