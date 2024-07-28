<template>
  <div class="flex h-dvh">
    <div class="flex justify-between bg-dirty-gray">
      <div class="flex flex-col">
        <div
          id="logo"
          class="flex justify-center bg-primary-gray text-white p-3"
        >
          Logo
        </div>

        <div
          id="nav"
          class="flex flex-col h-full items-center list-none p-1 py-5 m-0"
        >
          <NuxtLink class="nav-item" to="/home"> Home </NuxtLink>
          <NuxtLink class="nav-item" to="/devices"> Devices </NuxtLink>
        </div>
      </div>
    </div>

    <slot></slot>
  </div>
</template>

<style scoped lang="css"></style>
