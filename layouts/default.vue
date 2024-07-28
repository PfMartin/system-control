<template>
  <div class="bg-secondary-gray text-primary-white flex h-dvh">
    <NavBar :routes-config="routesConfig" />
    <slot></slot>
  </div>
</template>

<script setup lang="ts">
import type { RoutesConfig } from '~/components/NavBar.vue';

const routesConfig: RoutesConfig[] = [
  {
    name: 'Home',
    path: '/',
    icon: 'uil:home-alt',
  },
  {
    name: 'Devices',
    path: '/devices',
    icon: 'uil:processor',
  },
  {
    name: 'Config',
    path: '/config',
    icon: 'uil:cog',
  },
];
</script>

<style scoped lang="css"></style>
