<template>
  <div>
    <div class="ml-auto rounded-full h-20 w-20 bg-green-600 flex justify-center items-center text-white text-4xl cursor-pointer hover:shadow-xl" v-on:click="openModal">
      <IconPlusLg></IconPlusLg>
    </div>

    <BaseModal :is-open="isOpen" @close="closeModal">
      <div class="flex justify-between items-center mb-2">
        <h2 class="text-2xl font-bold">Registrar Tarea</h2>
        <div @click="closeModal" class="ml-auto rounded-full flex h-8 w-8 justify-center items-center bg-red-600 hover:shadow-xl text-white cursor-pointer">X</div>
      </div>
      <div class="flex flex-col gap-4 py-4">
        <div>
          <label for="nombre" class="block">Nombre:</label>
          <input type="text" id="nombre" class="input-field" v-model="nombre"/>
        </div>
        <div>
          <label for="descripcion" class="block">Descripción:</label>
          <textarea id="descripcion" class="input-field" v-model="descripcion"></textarea>
        </div>
        <div>
          <label for="fecha-inicio" class="block">Fecha de inicio:</label>
          <input type="date" id="fecha-inicio" class="input-field" v-model="fechaInicio"/>
        </div>
        <div>
          <label for="fecha-fin" class="block">Fecha de fin:</label>
          <input type="date" id="fecha-fin" class="input-field" v-model="fechaFin"/>
        </div>
        <div>
          <label for="importancia" class="block">Importancia:</label>
          <select id="importancia" class="input-field" v-model="importancia">
            <option value="alta">Muy importante</option>
            <option value="normal">Normal</option>
            <option value="baja">Bajo</option>
          </select>
        </div>
      </div>

      <div class="flex justify-end mt-4 gap-4">
        <button @click="closeModal" class="btn-primary bg-red-600 text-white font-medium p-2 rounded-lg hover:shadow-xl">Cerrar</button>
        <button @click="submitForm" class="btn-primary bg-green-600 text-white font-medium p-2 rounded-lg hover:shadow-xl">Registrar</button>
      </div>
    </BaseModal>
  </div>
</template>

<script lang="ts" setup>
import {ref} from 'vue';
import BaseModal from '../BaseModal/BaseModal.vue';
import IconPlusLg from "../../icons/IconPlusLg.vue";

const isOpen = ref(false)
const nombre = ref('')
const descripcion = ref('')
const fechaInicio = ref('')
const fechaFin = ref('')
const importancia = ref('alta')

const openModal = () => {
  isOpen.value = true
};

const closeModal = () => {
  isOpen.value = false
};

const submitForm = () => {
  // Aquí puedes realizar la lógica para enviar el formulario
  // Puedes acceder a los valores de los campos utilizando las variables ref

  // Por ejemplo:
  console.log(nombre.value);
  console.log(descripcion.value);
  console.log(fechaInicio.value);
  console.log(fechaFin.value);
  console.log(importancia.value);

  closeModal();
}
</script>

<style scoped>
.input-field {
  padding: 0.5rem;
  border: 1px solid #ccc;
  border-radius: 0.25rem;
  width: 100%;
}
</style>


