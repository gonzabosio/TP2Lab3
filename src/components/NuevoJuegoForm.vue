<template>
    <div class="contenidoForm">
        <h4>Nuevo videojuego</h4>
        
        <form @submit.prevent="submitForm">
            <div class="form-grupo">
                <label>Nombre*</label>
                <input id="nombre" type="text" name="name" v-model="nombre"/>
            </div>
            <div class="form-grupo">
                <label>Plataforma*</label>
                <select id="plataforma" name="plataforma" v-model="plataforma">
                    <option>PC</option>
                    <option>PlayStation</option>
                    <option>Xbox One</option>
                </select>
            </div>
            <div class="form-grupo">
                <label>Estado*</label>
                <select id="estado" name="estado" v-model="estado">
                    <option>Pendiente</option>
                    <option>Jugando</option>
                    <option>Completado</option>
                </select>
            </div>
            <div class="form-grupo">
                <label>Puntaje</label>
                <input id="puntaje" type="number" name="puntaje" max="10" min="1" v-model="puntaje">
            </div>
            <button type="submit">Registrar</button>
        </form>
        <ul>
            <li v-for="(error, index) in errors" :key="index">{{ error }}</li>
        </ul>
    </div>
</template>

<script>
    export default {
        name: 'JuegoForm',
        data() {
            return {
                nombre: '',
                plataforma: '',
                estado: '',
                puntaje: null,
                errors: []
            };
        },
        methods: {
            submitForm() {
                this.errors = []
                if(this.nombre == '') {
                    this.errors.push('Ingrese un nombre')
                }
                if(this.plataforma == '') {
                    this.errors.push('Ingrese una plataforma')
                }
                if(this.estado == '') {
                    this.errors.push('Ingrese el estado del juego')
                }
                if(this.puntaje == '') {
                    if(!this.puntaje >= 0 || !this.puntaje <= 10) {
                        this.errors.push('Ingrese un puntaje del 1 al 10')
                    }
                }
                else {
                    const formData = {
                    nombre: this.nombre,
                    plataforma: this.plataforma,
                    estado: this.estado,
                    puntaje: this.puntaje
                    }
                    console.log(formData);
                    this.resetForm()
                }
            },
            resetForm() {
                this.nombre = "",
                this.plataforma = "",
                this.estado = "",
                this.puntaje = null
            }
        }
    }
</script>
<style>
    .form-grupo {
        display: flex;
        align-items: center;
        margin-bottom: 20px; 
    }
    label {
        width: 100px;
    }
    input {
        width: 190px;
    }
    select {
        width: 198px;
    }
    ul {
        color: red
    }
</style>