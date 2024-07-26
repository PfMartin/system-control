<template>
  <div class="flex justify-between w-screen bg-gray-700">
    <div class="flex">
      <div id="logo" class="bg-gray-900 text-white p-3">Logo</div>

      <ul id="nav" class="flex items-center bg-blue-200 list-none p-0 m-0">
        <li class="p-2 m-1 hover:bg-indigo-500 rounded">
          <NuxtLink to="/home">Home</NuxtLink>
        </li>
        <li class="p-2 m-1 hover:bg-indigo-500 rounded">
          <NuxtLink to="/devices">Devices</NuxtLink>
        </li>
      </ul>
    </div>

    <div id="search" class="flex items-center">Search</div>
  </div>
  <slot></slot>
</template>
