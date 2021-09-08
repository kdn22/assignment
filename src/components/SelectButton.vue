<template>
  <div v-show="showSelectButton">
    <h2>{{ text }}</h2>
    <select v-model="selectedOption" @change="onChange">
      <option v-for="pokemon in pokemons" :key="pokemon" :value="pokemon.url">
        {{ pokemon.name }}
      </option>
    </select>
  </div>
</template>

<script>
export default {
  name: "SelectButton",
  props: {
    pokemons: Array,
    showSelectButton: Boolean,
    text: String,
  },
  emits: ["fetch-pokemon"],
  data() {
    return {
      selectedOption: "",
    };
  },
  methods: {
    onChange(e) {
      this.$emit("fetch-pokemon", e.target.value);
    },
  },
};
</script>

<style scoped>
div {
  position: absolute;
  top: 0;
  left: calc(50% - 175px);
}
h2 {
  padding-top: 2rem;
  user-select: none;
}
select {
  height: 50px;
  width: 350px;
  border: none;
  box-shadow: inset 0 0 20px rgba(255, 203, 5, 0.7);
  border-radius: 5px;
  color: #333;
  font-size: 3rem;
  text-align: center;
  text-transform: capitalize;
  outline: none;
  margin-top: 2rem;
}
select:hover {
  cursor: pointer;
}
option {
  font-family: monospace;
  font-size: 1.5rem;
}
</style>