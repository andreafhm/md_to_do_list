<template>
  <div class="flex flex-col gap-8 p-12">
    <div class="flex w-full text-2xl font-bold text-gray-700">Mis Actividades</div>
    <div class="grid grid-cols-2 sm:grid-cols-4 gap-5 h-40">
      <ResumeCard :amount="35" :resume-type="'all'" :url="'/all'"></ResumeCard>
      <ResumeCard :amount="5" :resume-type="'day'" :url="'/day'"></ResumeCard>
      <ResumeCard :amount="10" :resume-type="'week'" :url="'/week'"></ResumeCard>
      <ResumeCard :amount="20" :resume-type="'month'" :url="'/month'"></ResumeCard>
    </div>
    <div class="h-full grid grid-cols-2 gap-5">
      <div class="flex flex-col">
        <div class="flex justify-between items-center mx-5 mb-8">
          <span class="text-2xl font-bold text-gray-700">Mis listas</span>
          <a class="cursor-pointer hover:underline"><span class="font-semibold text-gray-600">Ver más</span></a>
        </div>
        <BaseCard>
          <div class="h-full flex flex-col justify-between">
            <BaseTable :headers="headers1" :rows="rows1"></BaseTable>
            <AddTaskModal></AddTaskModal>
          </div>
        </BaseCard>
      </div>
      <div class="flex flex-col">
        <div class="flex justify-between items-center mx-5 mb-8">
          <span class="text-2xl font-bold text-gray-700">Tareas importantes</span>
          <a class="cursor-pointer hover:underline"><span class="font-semibold text-gray-600">Ver más</span></a>
        </div>
        <BaseCard>
          <div class="h-full flex flex-col justify-between">
            <BaseTable :headers="headers1" :rows="rows1"></BaseTable>
            <AddTaskModal></AddTaskModal>
          </div>
        </BaseCard>
      </div>
    </div>
  </div>
</template>

<script setup>
import BaseCard from "../components/cards/BaseCard/BaseCard.vue";
import BaseTable from "../components/Table/BaseTable/BaseTable.vue";
import ResumeCard from "../components/cards/ResumeCard/ResumeCard.vue";
import AddTaskModal from "../components/modal/AddTaskModal/AddTaskModal.vue";

const headers1 = [{value: 'N°', style: 'w-12'}, {value: 'Nombre', style: 'w-1/3' }, {value: 'Descripción', style: 'w-full'}]
const rows1 = [
  [{ value:'1', style:'text-center align-middle font-medium'}, { value:'Proyecto de Continuidad', style:'align-middle font-medium' }, { value:'Tareas correspondientes al proyecto de Gestión de Continuidad del Negocio', style:'text-gray-400 font-medium' }],
  [{ value:'2', style:'text-center align-middle font-medium'}, { value:'Tareas de casa', style:'align-middle font-medium' }, { value:'Obligaciones y responsabilidades!!!', style:'text-gray-400 font-medium' }],
  [{ value:'3', style:'text-center align-middle font-medium'}, { value:'Aprendizaje', style:'align-middle font-medium' }, { value:'Cursos y más :D', style:'text-gray-400 font-medium' }]
]
</script>