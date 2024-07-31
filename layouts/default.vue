<template>
  <div class="flex h-dvh bg-secondary-gray text-primary-white">
    <NavBar :routes-config="routesConfig" />
    <div id="content" class="w-screen">
      <div class="flex h-14 items-center justify-between bg-primary-gray">
        <h2 class="p-4">{{ activeRoute }}</h2>
        <div id="search" class="flex items-center gap-2 p-4">
          <Icon name="uil:search"></Icon>
          <p>Search</p>
        </div>
      </div>
      <slot></slot>
    </div>
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

const route = useRoute();

const activeRoute = computed(() => route.meta.groupName);
</script>

<style scoped lang="css"></style>
