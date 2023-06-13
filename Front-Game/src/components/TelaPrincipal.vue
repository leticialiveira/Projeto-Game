<script setup>

</script>

<template>
  <div class="test">

    <img alt="logo Hile" class="logo" src="../assets/Logo-Projeto-Game.png" width="125" height="125" />
    <div class="greetings">
      <h1 class="title">Projeto Game</h1>
      <router-link to="/game">Clique aqui e entre em um mundo de jogos.</router-link>
      <span> Front + Back</span>
    </div>
  </div>
</template>

<style scoped>

.test {
  display: flex;
  flex-direction: row;
  gap: 30px;
}
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  top: -10px;
  color: white ;
}

h3 {
  font-size: 1.2rem;
}

.greetings {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
