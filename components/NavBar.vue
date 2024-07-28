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
          <NuxtLink class="nav-item" to="/home"> Home </NuxtLink>
          <NuxtLink class="nav-item" to="/devices"> Devices </NuxtLink>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts"></script>
