<script setup>
import TelaGame from '../components/TelaGame.vue'
import axios from "axios";
import { ref } from "vue";
// import Json from '../mock/grid-games.json'

// let testando = ref(Json)
// let isLoading = ref(true)
let dataAxios = ref([])

async function Test() {
  await axios.get("http://gameapi-prod.up.railway.app/games")
    .then((response) => {
      dataAxios.value = response.data;
      dataAxios = dataAxios.value
      // isLoading.value = true
      // console.log(isLoading.value);
    })
    .catch((error) => {
      console.log(error);
    });
  }
  await Test();

console.log(dataAxios);
let jsonAxios = JSON.stringify(dataAxios)
console.log(jsonAxios);

</script>

<template>
  <div class="game"> 
    <div class="grid-games">
      <!-- v-if="isLoading"  -->
      <TelaGame  v-for="item in jsonAxios" :key="item.id" :title="item.title" :imgUrl="item.imgUrl" :year="item.year" 
      :shortDescription="item.shortDescription" /> 
    </div>
  </div> 
</template>

<style scoped>
.grid-games {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  width: 100%;
  height: auto;
  gap: 50px;
}
</style>