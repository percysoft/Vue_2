<template>
    <ul class="list-group">
            <li v-for="(tarea, indice) of tareas"
                class="list-group-item"
               :class="{terminada: tarea.terminada}"
               :key="indice">
                {{ tarea.texto }}
                <span class="pull-right">
                    <button
                    type="button"
                    class="btn btn-success btn-xs glyphicon glyphicon-ok"
                    v-on:click="tarea.terminada = !tarea.terminada"
                    >
                    Terminado
                    </button>
                    <button
                    type="button"
                    class="btn btn-danger btn-xs glyphicon glyphicon-ok"
                    v-on:click="borrar(indice)"
                    >
                    Eliminar
                    </button>
                </span>
            </li>
        </ul>
</template>

<script>
export default {
    props:['tareas'],
    methods: {
        borrar: function(indice){
            this.tareas.splice(indice,1);
        }
    }
}
</script>
<style scope>
    .terminada {
        color: gray;
        text-decoration: line-through;
    }
</style>
