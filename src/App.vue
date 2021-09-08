<template>
  <FetchButton
    @fetch-poke-api="fetchPokeApi"
    :showFetchButton="showFetchButton"
  />

  <SelectButton
    text="Vyber si Pokémona:"
    :pokemons="pokemons"
    @fetch-pokemon="fetchPokemon"
    :showSelectButton="showSelectButton"
  />

  <PokemonCard />
</template>

<script>
import FetchButton from "./components/FetchButton.vue";
import SelectButton from "./components/SelectButton.vue";
import PokemonCard from "./components/PokemonCard.vue";

export default {
  name: "App",
  components: {
    FetchButton,
    SelectButton,
    PokemonCard,
  },
  data() {
    return {
      pokemons: [],
      showFetchButton: true,
      showSelectButton: false,
    };
  },
  methods: {
    async fetchPokeApi() {
      const res = await fetch("https://pokeapi.co/api/v2/pokemon?limit=9");
      const data = await res.json();
      const pokeInfo = data.results;

      this.pokemons = pokeInfo;
      this.showFetchButton = !this.showFetchButton;
      this.showSelectButton = !this.showSelectButton;

      return data;
    },
    async fetchPokemon(event) {
      let res = await fetch(event);
      let data = await res.json();

      document.querySelector("h1").innerHTML = data.name;
      document.querySelector("img").src = data.sprites.front_default;
      document.querySelector(".pokeCard").style.display = "flex";

      return data;
    },
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=VT323&display=swap");
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "VT323", monospace;
}
#app {
  position: relative;
  background: rgba(255, 203, 5, 0.7);
  text-align: center;
  color: rgb(0, 58, 112);
}
</style>
