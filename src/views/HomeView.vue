<script setup>
import {computed, onMounted, reactive, ref} from "vue";
import ListPokemons from "@/components/ListPokemons.vue";
import CardPokemonSelected from "@/components/CardPokemonSelected.vue";
import axios from "axios";

let urlPokemonList = ref("https://pokeapi.co/api/v2/pokemon?limit=151&offset=0");
let baseUrlSvg = ref("https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/");
let pokemons = reactive(ref());
let searchPokemon = ref("");
let pokemonSelected = reactive(ref());

onMounted(() => {
  axios.get(urlPokemonList.value)
      .then(res => pokemons.value = res.data.results);
})

const pokemonsFiltered = computed(() => {
  if (pokemons.value && searchPokemon.value) {
    return pokemons.value.filter(
        pokemon => pokemon.name.toLowerCase().includes(searchPokemon.value.toLowerCase())
    )
  }
  return pokemons.value;
})

const selectPokemon = async (pokemon) => {
  axios.get(pokemon.url)
      .then(res => pokemonSelected.value = res.data);
}
</script>

<template>
  <main>
    <div class="container text-body-secondary">
      <div class="row mt-4">
        <div class="col-sm-12 col-md-6">
          <CardPokemonSelected
              :name="pokemonSelected?.name"
              :xp="pokemonSelected?.base_experience"
              :height="pokemonSelected?.height"
              :image="pokemonSelected?.sprites.other.dream_world.front_default"
              :id="pokemonSelected?.id"
              :weight="pokemonSelected?.weight"
          ></CardPokemonSelected>
        </div>
        <div class="col-sm-12 col-md-6">
          <div class="card card-list">
            <div class="card-body row">
              <div class="mb-3">
                <label hidden for="searchPokemon" class="form-label">Email address</label>
                <input v-model="searchPokemon" type="text" class="form-control" id="searchPokemon"
                       placeholder="Pokemon name">
              </div>
              <ListPokemons
                  v-for="pokemon in pokemonsFiltered"
                  :key="pokemon.name"
                  :name="pokemon.name"
                  :baseUrlSvg="baseUrlSvg + pokemon.url.split('/')[6] + '.svg'"
                  @click="selectPokemon(pokemon)">
              </ListPokemons>
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<style scoped>
.card-list {
  overflow-y: scroll;
  height: 75vh;
  overflow-x: hidden;;
}
</style>
