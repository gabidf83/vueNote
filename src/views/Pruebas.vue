<template>
  <div>
    <h1>Esta es la prueba</h1>
    <InsertarTarea @NuevaTarea="(tarea:string)=>AnadirTarea(tarea)" />
    <ListaTareas :tareas="listaTareas" @BorrarTarea="(id:number)=>BorrarTarea(id)"/>
  </div>
</template>

<script setup lang="ts">
//IMPORTS
import InsertarTarea from "@/components/InsertarTarea.vue";
import ListaTareas from "@/components/ListaTareas.vue";
import { ref } from "vue";
//VARIABLES
const listaTareas = ref([] as string[]);

//FUNCIONES
const AnadirTarea = (tarea: string) => {
  console.log("Tarea Añadidad: ", tarea);
  listaTareas.value.push(tarea);
};
const BorrarTarea = (id: number) => {
  listaTareas.value.splice(id,1);
}

</script>

<style scoped></style>
