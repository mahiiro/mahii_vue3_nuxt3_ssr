<template>
  <nav class="fixed-top navbar navbar-expand-md navbar-light bg-light">
    <div class="container-fluid">
      <NuxtLink to="/">Mahii</NuxtLink>
      <button @click="toggleNavbar()" type="button" class="navbar-toggler">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div id="navbar" class="justify-content-end navbar-collapse" :class="{ collapse: navbarCollapsed }">
        <ul class="navbar-nav">
          <li class="nav-item">
            <NuxtLink class="nav-link" to="page">Page</NuxtLink>
          </li>
          <li class="nav-item">
            <span class="nav-link" @click="chatAction()" >Open chat with click</span>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script setup lang="ts">
  import { ref } from 'vue';
  const navbarCollapsed = ref<boolean>(true);

  const emit = defineEmits<{
    (e: 'openChat'): void;
  }>();

  function chatAction() {
    console.log(`Chat was clicked`);
    emit('openChat');
  }
</script>