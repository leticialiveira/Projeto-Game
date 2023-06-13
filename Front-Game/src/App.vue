<script setup>
import { RouterView } from 'vue-router';
// import JsonGame from './mock/grid-games.json'
// import { ref } from "vue";
// import TelaGame from './components/TelaGame.vue'
// import TelaPrincipal from './components/TelaPrincipal.vue'

// let json = ref(JsonGame)

</script>

<template>
  <router-view></router-view>


  <!-- <div class="grid-games">
      <TelaGame v-for="item in json" :key="item.title" :title="item.title" :image="item.image" :year="item.year"
      :description="item.description" />
    </div> -->
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }


  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}


</style>
