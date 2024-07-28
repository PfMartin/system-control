<template>
  <div class="flex h-dvh">
    <div class="flex justify-between bg-dirty-gray">
      <div class="flex flex-col">
        <div
          id="logo"
          class="flex justify-center bg-primary-gray p-3 text-white"
        >
          Logo
        </div>

        <div
          id="nav"
          class="m-0 flex h-full list-none flex-col items-center p-1 py-5"
        >
          <NuxtLink
            v-for="route in routesConfig"
            :key="route.name"
            :class="[
              'nav-item',
              isCurrentPath(route.path) ? 'nav-item-selected' : '',
            ]"
            :to="route.path"
          >
            <Icon v-if="!!route.icon" :name="route.icon" />
            <span v-else>{{ route.name }}</span>
          </NuxtLink>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
export interface RoutesConfig {
  name: string;
  path: string;
  icon?: string;
  subroutes?: RoutesConfig;
}

defineProps<{
  routesConfig: RoutesConfig[];
}>();

const route = useRoute();
const isCurrentPath = (path: string) => path === route.fullPath;
</script>
