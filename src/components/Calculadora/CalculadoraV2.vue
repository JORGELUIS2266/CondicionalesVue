<script>
    export default{
        data() {
            return {
                display:'',
                currentValue:0,

            }
        },
        methods:{
            agregarNumero(Numero){
                this.display += Numero;
            },
            calculo(){
                try {
                    this.currentValue = eval(this.display);
                    this.display = this.currentValue.toString();
                    
                } catch (error) {
                    this.display='Error';

                }
                
            },
            limpiarDisplay(){
                this.display=''; 
            },

            eliminarNumero(){
                this.display = this.display.slice(0,-1);
            }
        }
    }
</script>
<template>
<div class="container d-flex justify-contenet-center" style="height: 360px; background-color: black;">
    <div class="card p-3" style="width: 300px; background-color:#8cbdfc;">
        <div class="card-body">
            <h6 class="text-center">Calculadora</h6>
            <!-- Display de la Calculadora -->
             <div class="mb-3">
                <input type="text" class="form-control" v-model="display" disabled>
             </div>
             <!-- Botones de la calculadora -->
             <div class="d-flex justify-content-between">
                <button class="btn btn-primary" @click="agregarNumero('%')">%</button>
                <button class="btn btn-danger" @click="limpiarDisplay">CE</button>
                <button class="btn btn-danger" @click="limpiarDisplay">C</button>
                <button class="btn btn-danger" @click="eliminarNumero">B</button>
              </div>

              <div class="d-flex justify-content-between mt-2">
                <button class="btn btn-secondary" @click="agregarNumero(7)">7</button>
                <button class="btn btn-secondary" @click="agregarNumero(8)">8</button>
                <button class="btn btn-secondary" @click="agregarNumero(9)">9</button>
                <button class="btn btn-primary" @click="agregarNumero('/')">/</button>
              </div>
              <div class="d-flex justify-content-between mt-2">
                <button class="btn btn-secondary" @click="agregarNumero(4)">4</button>
                <button class="btn btn-secondary" @click="agregarNumero(5)">5</button>
                <button class="btn btn-secondary" @click="agregarNumero(6)">6</button>
                <button class="btn btn-primary" @click="agregarNumero('*')">*</button>
              </div>
              <div class="d-flex justify-content-between mt-2">
                <button class="btn btn-secondary" @click="agregarNumero(1)">1</button>
                <button class="btn btn-secondary" @click="agregarNumero(2)">2</button>
                <button class="btn btn-secondary" @click="agregarNumero(3)">3</button>
                <button class="btn btn-primary" @click="agregarNumero('-')">-</button>
              </div>

              <div class="d-flex justify-content-between mt-2">
                <button class="btn btn-secondary" @click="calculo">=</button>
                <button class="btn btn-secondary" @click="agregarNumero(0)">0</button>
                <button class="btn btn-secondary" @click="agregarNumero('.')">.</button>
                <button class="btn btn-primary" @click="agregarNumero('+')">+</button>
              </div>
        </div>
    </div>
</div>
</template>
<style> 
button{
    width: 50px;
    height: 40px;
    font-size: 10px;
    text-align: center;
}
h6{
    font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
}

</style>