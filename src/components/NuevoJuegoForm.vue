<template>
    <div class="contenidoForm">
        <h4>Nuevo videojuego</h4>
        
        <form @submit.prevent="submitForm">
            <div class="form-grupo">
                <label>Nombre</label>
                <input id="nombre" type="text" name="name" v-model="nombre"/>
            </div>
            <div class="form-grupo">
                <label>Plataforma</label>
                <input id="plataforma" type="text" name="plataforma" list="elegirPlataforma" v-model="plataforma"/>
                <datalist id="elegirPlataforma">
                    <option>PC</option>
                    <option>PlayStation</option>
                    <option>Xbox One</option>
            </datalist>
            </div>
            <div class="form-grupo">
                <label>Estado</label>
                <input id="estado" type="text" name="estado" list="elegirEstado" v-model="estado"/>
                <datalist id="elegirEstado">
                    <option>Pendiente</option>
                    <option>Jugando</option>
                    <option>Completado</option>
            </datalist>
            </div>
            <div class="form-grupo">
                <label>Puntaje</label>
                <input id="puntaje" type="number" name="puntaje" max="10" min="1" value="1" v-model="puntaje">
            </div>
            <button type="submit">Registrar</button>
        </form>
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
                puntaje: 1
            };
        },
        methods: {
            submitForm() {
                const formData = {
                    nombre: this.nombre,
                    plataforma: this.plataforma,
                    estado: this.estado,
                    puntaje: this.puntaje
                }
                console.log(formData);
                this.resetForm()
            },
            resetForm() {
                this.nombre = "",
                this.plataforma = "",
                this.estado = "",
                this.puntaje = 1
            },
            showAlert() {
                alert('Añadir a la lista')
            },
        }
    }
</script>
<style>
    .form-grupo {
        display: flex;
        align-items: center;
        margin-bottom: 10px; 
    }
    label {
        width: 100px;
    }
</style>