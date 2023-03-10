<script setup>
const pokemon = defineProps(["name", "image"])
</script>

<template>
  <div
      class="p-1 rounded-lg hover:cursor-pointer m-2 bg-gradient-to-t from-blue-500 hover:from-blue-700 dark:from-blue-900 dark:hover:from-blue-700 flex-col justify-around">
    <p class="text-center text-xs lg:font-medium lg:text-base dark:text-slate-300 pb-2">
      {{ name.charAt(0).toUpperCase() + name.slice(1) }}
    </p>
    <img class="p-1" :src="image" :alt="pokemon.name" height="80">
  </div>
</template>

<style>
</style>
