<template>
  <div>
    <v-row>
      <v-col cols="6">
        <v-text-field label="Inserte la tarea" v-model="tarea"></v-text-field>
      </v-col>
      <v-col cols="2">
        <v-btn @click="AnadirTarea()"> añadir </v-btn>
      </v-col>
    </v-row>
  </div>
</template>

<script setup lang="ts">
//IMPORTS
import { ref } from "vue";
//VARIABLES
const emit = defineEmits<{
  (e: "NuevaTarea", tarea: string): void;
}>();
const tarea = ref("");

//FUNCIONES

const AnadirTarea = function () {
  console.log(tarea);
  tarea.value = tarea.value.toUpperCase();
  emit("NuevaTarea", tarea.value);
  tarea.value = "";
};
</script>

<style scoped></style>
