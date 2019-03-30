<template>
  <div id="app" class="container">
      <div class="jumbotron">
        <!-- <Titulo :titulo="titulo" :numTareas="numTareas"></Titulo> -->
        <Titulo :titulo="titulo"></Titulo>
        <!-- {{ numTareas }} -->
        <!-- <nueva-tarea
        :tareas="tareas"
        v-on:incrementarContador="numTareas += $event"
        ></nueva-tarea> -->
        <nueva-tarea
        :tareas="tareas"
        :actualizarContador="actualizarContador"
        ></nueva-tarea>
        <lista-tareas :tareas="tareas"></lista-tareas>
      </div>
  </div>
</template>

<script>
import Titulo from './components/TituloComponent.vue'
import NuevaTarea from './components/nuevaTareaComponent'
import ListaTareas from './components//listaTareasComponent'

export default {
  components: {
    Titulo,
    NuevaTarea,
    ListaTareas
  },
  data () {
    return {
      titulo: 'Lista de tareas',
      // numTareas: 3,
       tareas: [
        {
            texto: 'Aprender vue.js',
            terminada: false
        },
        {
            texto: 'Aprender Angular 2',
            terminada : false
        },
        {
            texto: 'Aprender Ionic 2',
            terminada : false
        }
      ]
    }
  },
  methods: {
    actualizarContador () {
      this.numTareas++;
    }
  },
}
</script>

<style>

</style>
