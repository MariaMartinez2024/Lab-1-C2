
<template>
  <div>
    <h1>Gestor de Tareas</h1>
    <input v-model="nuevaTarea" placeholder="Escribe una tarea" />
    <button @click="agregarTarea">Agregar</button>
    <p v-if="error" style="color:red">{{ error }}</p>
    <ul>
      <li v-for="(tarea, index) in tareas" :key="index">
        <span :class="{completada: tarea.completada}">
          {{ tarea.texto }}
        </span>
        <button @click="completarTarea(index)">✔</button>
        <button @click="eliminarTarea(index)">❌</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      nuevaTarea: "",
      tareas: [],
      error: ""
    };
  },
  methods: {
    agregarTarea() {
      if (this.nuevaTarea.trim() === "") {
        this.error = "La tarea no puede estar vacía";
      } else {
        this.tareas.push({ texto: this.nuevaTarea, completada: false });
        this.nuevaTarea = "";
        this.error = "";
      }
    },
    completarTarea(index) {
      this.tareas[index].completada = true;
    },
    eliminarTarea(index) {
      this.tareas.splice(index, 1);
    }
  }
};
</script>

<style>
.completada {
  text-decoration: line-through;
  color: gray;
}
</style>
