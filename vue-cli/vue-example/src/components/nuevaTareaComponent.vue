<template>
     <div class="input-group">
        <input
        type="text"
        placeholder="Escribe una nueva tarea"
        v-model="nuevaTarea"
        class="form-control"
        v-on:keyup.enter="agregarTarea"
        >
        <span class="innput-group-btn">
            <button
            type="button"
            v-on:click="agregarTarea"
            class="btn btn-primary">
            Agregar
            </button>
        </span>
    </div>
</template>

<script>
import { bus } from '../main';

export default {
    data () {
        return {
            nuevaTarea: ''
        }
    },
    props: ['tareas', "actualizarContador"],
    methods: {
        agregarTarea () {
            var texto = this.nuevaTarea.trim();
            if(texto) {
                this.tareas.push({
                    texto,
                    terminada: false,
                })
                bus.actualizarContador(this.tareas.length);
                // bus.$emit('actualizarContador', this.tareas.length);
                // this.actualizarContador();
                // this.$emit('incrementarContador',1);
            }
            this.nuevaTarea= ""
        }
    },
    created () {
    //    bus.$emit('actualizarContador', this.tareas.length);
     bus.actualizarContador(this.tareas.length);
    }
}
</script>
