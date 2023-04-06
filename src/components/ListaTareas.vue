<template>
  <div class="v-container">
    <ul>
      <li v-for="tarea in tareas">
        <v-btn :id="tareas.indexOf(tarea)" icon="mdi-delete-outline" @click="BorrarTarea(tareas.indexOf(tarea))"></v-btn>
        <v-divider class="mx-3 align-self-center" length="24" thickness="2" vertical></v-divider>
        {{ tarea }}
      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">import { ref } from 'vue';

defineProps<{
  tareas: string[];
}>();
const emit = defineEmits<{
  (e: "BorrarTarea", id: number): void;
}>();
const id = ref(0);

const BorrarTarea = (id) => {
  emit("BorrarTarea", id);
}
</script>

<style scoped>
li{
  list-style:none;
}
</style>
