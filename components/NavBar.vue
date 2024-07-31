<template>
  <div class="flex" @mouseleave="hoveredRoute && collapseSubroutes()">
    <div id="nav-bar" class="flex flex-col bg-dirty-gray">
      <div
        id="logo"
        class="flex justify-center bg-primary-gray p-3 text-primary-white"
      >
        <NuxtLink class="text-primary-white" :to="routesConfig[0].path">
          <Icon
            class="text-3xl transition-colors hover:text-electric-violet-1"
            name="uil:server-network"
          />
        </NuxtLink>
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
          @mouseenter="
            route.subroutes ? expandSubroutes(route) : collapseSubroutes()
          "
        >
          <Icon v-if="!!route.icon" :name="route.icon" />
          <span v-else>{{ route.name }}</span>
        </NuxtLink>
      </div>
    </div>

    <div
      v-if="hoveredRoute"
      id="sub-nav-popup"
      class="absolute left-14 h-dvh bg-primary-gray transition-all"
    >
      <div class="flex flex-col">
        <h4 class="m-1 mb-4 p-2">{{ hoveredRoute.name }}</h4>
        <div>
          <NuxtLink
            v-for="subroute in hoveredRoute.subroutes"
            :key="subroute.name"
            :to="subroute.path"
            class="m-1 flex flex-col rounded p-2 text-primary-white no-underline transition-colors hover:cursor-pointer hover:bg-electric-violet-1"
            >{{ subroute.name }}</NuxtLink
          >
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
  subroutes?: {
    name: string;
    path: string;
  }[];
}

defineProps<{
  routesConfig: RoutesConfig[];
}>();

const route = useRoute();

// TODO: Set current path to first level path, in order to highlight the selected path
const isCurrentPath = (routePath: string) => {
  const separator = new RegExp('\/');
  return routePath.split(separator)[1] === route.path.split(separator)[1];
};

const hoveredRoute = ref<RoutesConfig | null>(null);
const expandSubroutes = (route: RoutesConfig) => {
  hoveredRoute.value = route;
};

const collapseSubroutes = () => {
  hoveredRoute.value = null;
};
</script>
