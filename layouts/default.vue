<template>
  <div class="flex h-dvh bg-secondary-gray text-primary-white">
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
    subroutes: [
      {
        name: 'Overview',
        path: '/devices',
      },
      {
        name: 'Configuration',
        path: '/devices/config',
      },
    ],
  },
  {
    name: 'Config',
    path: '/config',
    icon: 'uil:cog',
  },
];
</script>

<style scoped lang="css"></style>
