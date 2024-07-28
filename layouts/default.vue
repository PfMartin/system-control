<template>
  <NavBar :routes-config="routesConfig" />

  <slot></slot>
</template>

<script setup lang="ts">
import type { RoutesConfig } from '~/components/NavBar.vue';

const routesConfig: RoutesConfig[] = [
  {
    name: 'Home',
    path: '/home',
  },
  {
    name: 'Devices',
    path: '/devices',
  },
];
</script>

<style scoped lang="css"></style>
