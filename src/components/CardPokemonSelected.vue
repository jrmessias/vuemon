<script setup>
const pokemon = defineProps(["name", "xp", "height", "image", "id", "weight"])
</script>

<template>
  <div class="card cardPokemonSelected">
    <div class="text-center" v-if="pokemon.image">
      <img :src="pokemon.image" class="w-100" height="250" alt="">
    </div>
    <div class="text-center" v-else="pokemon.image">
      <img src="../assets/egg.svg" class="w-100" height="250" alt="">
    </div>
    <div class="card-body">
      <h5 class="card-title text-center">{{ pokemon.name || "???" }}</h5>
      <hr>
      <div class="row">
        <div class="col">
          <strong>Pokedéx: </strong>
        </div>
        <div class="col">#{{ pokemon.id }}</div>
        <div class="col">
          <strong>XP:</strong>
        </div>
        <div class="col">{{ pokemon.xp }}</div>
      </div>
      <div class="row">
        <div class="col">
          <strong>Peso: </strong>
        </div>
        <div class="col">{{ pokemon.weight }}</div>
        <div class="col">
          <strong>Altura:</strong>
        </div>
        <div class="col">{{ pokemon.height }}</div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.cardPokemonSelected{
  height: 75vh;
}
</style>
