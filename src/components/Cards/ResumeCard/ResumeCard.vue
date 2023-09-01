<template>
  <BaseCard>
    <div class="w-full">
      <div class="grid grid-cols-2">
        <div class="flex flex-col justify-center items-center gap-4">
          <IconAll v-if="resumeType == 'all'"/>
          <IconDayBlue v-if="resumeType == 'day'"/>
          <IconWeekBlue v-if="resumeType == 'week'"/>
          <IconMonthBlue v-if="resumeType == 'month'"/>
          <span class="text-black text-xl font-bold">
            {{ getTextResume(resumeType) }}
          </span>
        </div>
        <div class="flex flex-col justify-center items-center gap-4">
          <span class="text-gray-400 text-5xl font-bold">{{ amount }}</span>
          <IconNext class="cursor-pointer" v-on:click="alert(`Redirigido a ${url}`)"></IconNext>
        </div>
      </div>
    </div>
  </BaseCard>
</template>

<script lang="ts" setup>
import BaseCard from "../BaseCard/BaseCard.vue";
import IconNext from "../../icons/IconNext.vue";
import IconAll from "../../icons/IconAll.vue";
import IconDayBlue from "../../icons/IconDayBlue.vue";
import IconWeekBlue from "../../icons/IconWeekBlue.vue";
import IconMonthBlue from "../../icons/IconMonthBlue.vue";
import {computed} from "vue";

defineProps({
  resumeType: {
    type: String,
    validator: (value: string) => {
      const validValues = ['all', 'day', 'week', 'month'];
      return validValues.includes(value)
    }
  },
  amount: {
    type: Number
  },
  url: {
    type: String
  }
})

const getTextResume = (value: string) => {
  return computed ( () => {
    return value === 'all' ? 'Todas' :
              value === 'day' ? 'Mi día':
                  value === 'week' ? 'Mi semana':
                      value === 'month' ? 'Mi mes':''
  }).value
}

</script>