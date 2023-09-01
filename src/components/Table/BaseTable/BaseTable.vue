<template>
  <div class="w-full">
    <div class="flex flex-col">
      <div class="flex mb-4">
        <div class="font-bold border-b-2 border-gray-900 px-3" v-bind:class="head.style" v-for="head of headers">
          {{ head.value }}
        </div>
      </div>
      <div class="text-black">
        <div class="flex flex-col" v-for="(row, rindex) of rows">
          <div class="flex">
            <div v-for="(item, index) of row" class="flex-nowrap px-2" v-bind:class="item.style+' '+headers[index].style" >{{ item.value }}</div>
          </div>
          <div v-if="rindex < rows.length-1" class="my-5 border-b-2 border-gray-300"></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
defineProps<{
  headers: any[],
  rows: [any[]]
}>()
</script>

<style scoped>

</style>