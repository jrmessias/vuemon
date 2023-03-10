<script setup>
const pokemon = defineProps(["name", "xp", "height", "image", "id", "weight"])
</script>

<template>
  <div class="card py-4 rounded bg-gradient-to-t from-indigo-500 dark:from-indigo-900 text-slate-800 dark:text-slate-300">
    <div class="flex justify-center" v-if="pokemon.image">
      <img :src="pokemon.image" class="p-4" height="250" alt="">
    </div>
    <div class="flex justify-center" v-else="pokemon.image">
      <img src="../assets/egg.svg" class="p-4" height="250" alt="">
    </div>
    <div class="w-100 py-4">
      <h5 class="font-bold">{{ pokemon.name ? pokemon.name.charAt(0).toUpperCase() + pokemon.name.slice(1) : "???" }}</h5>
      <div class="grid grid-cols-2">
        <div class="">
          <span class="font-medium">Pokedéx:</span>
          <span class="col"> #{{ pokemon.id }}</span>
        </div>
        <div class="">
          <span class="font-medium">XP:</span>
          <span class="col"> {{ pokemon.xp}}</span>
        </div>
        <div class="">
          <span class="font-medium">Peso:</span>
          <span class="col"> {{ pokemon.weight }}</span>
        </div>
        <div class="">
          <span class="font-medium">Altura:</span>
          <span class="col"> {{ pokemon.height }}</span>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>

</style>
