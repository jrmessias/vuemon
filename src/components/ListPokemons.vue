<script setup>
const pokemon = defineProps(["name","baseUrlSvg"])

</script>

<template>
  <div class="col-4">
    <div class="card mb-3 cardListPokemon border-0 h-100">
      <p class="text-center">
        {{ name.charAt(0).toUpperCase() + name.slice(1) }}
      </p>
      <img
          class="card-img-top p-1"
          :src="baseUrlSvg"
      :alt="pokemon.name"
      height="80">
    </div>
  </div>
</template>

<style>

.cardListPokemon{
  background: #212529;
}
.cardListPokemon:hover{
  background: #2B3035;
  cursor: pointer;
}
.cardListPokemon img:hover{
  zoom: .95;
}
</style>
