<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import Sidebar from './components/Sidebar/Sidebar.vue'
</script>

<template>
  <div class="app">
    <Sidebar />
    <RouterView />
  </div>
  
</template>

<style lang="css">
:root {
  --primary: #00d1ff7d;
  --grey: #647489;
  --dark: #0F1D40;
  --dark-alt: #334155;
  --light: #d0e7ff;
  --sidebar-width: 280px;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background: var(--light);
}

button {
  cursor: pointer;
  appearance: none;
  border: none;
  outline: none;
  background: none;
}

.app {
  display: flex;

  main {
    flex: 1 1 0;
    padding: 2rem;

    @media (max-width: 768px) {
      padding-left: 6rem;
    }
  }
}
</style>
