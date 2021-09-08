<template>
  <button @click="$emit('fetch-poke-api')" v-show="showFetchButton">
    FETCH
  </button>
</template>

<script>
export default {
  name: "FetchButton",
  props: {
    showFetchButton: Boolean,
  },
};
</script>

<style scoped>
button {
  position: absolute;
  top: calc(50% - 25px);
  left: calc(50% - 75px);
  height: 50px;
  width: 150px;
  border: none;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
  color: #333;
  font-size: 3rem;
  text-align: center;
  margin: 2rem 0;
}

button:hover {
  cursor: pointer;
  color: #111;
}
</style>