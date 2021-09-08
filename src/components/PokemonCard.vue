<template>
  <div>
    <div class="pokeCard">
      <div class="sprite">
        <img src="" />
      </div>
      <div class="name">
        <h1></h1>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "PokemonCard",
};
</script>

<style scoped>
div {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100vw;
  height: 100vh;
}

.pokeCard {
  position: relative;
  display: none;
  flex-direction: column;
  width: 20vw;
  height: 50vh;
  background: whitesmoke;
  border: 7px solid;
  border-radius: 15px;
  box-shadow: 0 0 70px rgba(61, 125, 202, 0.7);
  margin: 5rem auto;
  transition: transform 0.75s ease-in-out;
}

.pokeCard:hover {
  transform: scale(1.1);
}

.name {
  width: 100%;
  height: 30%;
  background: radial-gradient(
    circle,
    rgba(204, 103, 25, 0.9) 30%,
    rgba(255, 5, 14, 0.9) 100%
  );
  border-top: 2px solid;
  border-radius: 0 0 8px 8px;
  filter: blur(0.8px);
}

h1 {
  color: #333;
  text-shadow: -1px 0 white, 0 1px rgb(204, 103, 25), 1px 0 purple,
    0 -1px rgb(61, 125, 202);
  font-size: 60px;
  text-transform: capitalize;
}

.name,
.sprite {
  display: flex;
  justify-content: center;
  align-items: center;
  user-select: none;
}

.sprite {
  height: 70%;
  width: 100%;
  background: url("../assets/spinning-background.gif") no-repeat center center;
  background-size: cover;
  border-radius: 8px 8px 0 0;
  filter: blur(1px);
}

img {
  width: 15rem;
}
</style>