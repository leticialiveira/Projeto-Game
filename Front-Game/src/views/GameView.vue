<script setup>
import TelaGame from '../components/TelaGame.vue'
import axios from "axios";
import { ref } from "vue";

let dataAxios = ref([])

function Test() {
  axios.get("http://gameapi-prod.up.railway.app/games")
    .then((response) => {
      dataAxios.value = response.data;
      dataAxios = dataAxios.value
    })
    .catch((error) => {
      console.log(error);
    });
}
Test();

</script>

<template>
  <div class="main">
    <header>
      <img src="../assets/Logo-Projeto-Game.png" alt="">
      <div class="links">
        <select name="desenvolvedores" id="" class="desenvolvedores-jogos">
          <option value="">Desenvolvedores</option>
          <optgroup label="Front-End">
            <option value="">Letícia Oliveira</option>
          </optgroup>
          <optgroup label="Back-End">
          <option value="">Alisson Mascarenhas</option>
        </optgroup>
        </select>

        <select name="jogos" id="" class="categorias">
          <option value="">Categorias</option>
          <option value="">Fantasia</option>
          <option value="">FPS</option>
        </select>

        <select name="jogos" id="" class="desenvolvedores-jogos">
          <option value="">Jogos</option>
          <option value="">Mass Effect Trilogy</option>
          <option value="">Red Dead Redemption 2</option>
          <option value="">The Witcher 3: Wild Hunt</option>
          <option value="">Sekiro: Shadows Die Twice</option>
          <option value="">Ghost of Tsushima</option>
          <option value="">Super Mario World</option>
          <option value="">Hollow Knight</option>
          <option value="">Ori and the Blind Forest</option>
          <option value="">Cuphead</option>
          <option value="">Sonic CD</option>
        </select>
      </div>
    </header>

    <div class="game">
      <div class="grid-games">
        <TelaGame v-for="item in dataAxios" :ref="dataAxios" :key="item.id" :title="item.title" :imgUrl="item.imgUrl"
          :year="item.year" :shortDescription="item.shortDescription" />
      </div>
    </div>
  </div>
</template>

<style scoped>
.main {
  padding-top: 10px;
}

header {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
}

header img {
  width: 120px;
}

header select {
  width: 220px;
  height: 40px;
  padding: 10px;
  
}

header .desenvolvedores-jogos{
  border: solid 1px #6C3483;
  border-radius: 5px;
  background-color: #6C3483;
  color: #D1F2EB;
}

header .categorias{
  border: solid 1px #D1F2EB;
  border-radius: 5px;
  background-color: #D1F2EB;
  color: #6C3483;
}
.main .game {
  padding-top: 200px;
  perspective: 700px;

}

.main .links{
  display: flex;
  width: auto;
  gap: 30px;
}
.grid-games {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  width: 100%;
  height: auto;
  gap: 50px;
}
</style>