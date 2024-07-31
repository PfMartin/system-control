<template>
  <div class="flex">
    <div
      class="header flex h-12 w-full content-center justify-between bg-dirty-gray p-2"
    >
      <button class="btn-primary flex">
        <Icon name="uil:plus"></Icon>Add device
      </button>
    </div>
  </div>
</template>

<script setup lang="ts">
definePageMeta({
  groupName: 'Devices Overview',
});
</script>
