<template>
  <div v-if="isOpen" class="fixed inset-0 flex items-center justify-center">
    <div class="modal-overlay">
      <div class="modal-container w-1/3">
        <div class="modal-content">
          <slot></slot>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts" setup>
defineProps<{isOpen: false}>()
const emit = defineEmits(['close'])
</script>

<style scoped>
.modal-overlay {
  z-index: 9999;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
}

.modal-container {
  max-width: 90%;
  max-height: 90%;
  overflow: auto;
}

.modal-content {
  background-color: white;
  padding: 2rem;
}
</style>