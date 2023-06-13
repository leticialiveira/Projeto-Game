<script setup>
defineProps({
        title: String,
        imgUrl:String,
        year: Number,
        shortDescription: String
    })

 
</script>

<template>
  <!-- <header> -->

    <!-- <img :src="image" alt=""> -->
  <!-- </header> -->
<article>
  <div class="header">
    <h1>{{title}}</h1>
  </div>
  <img :src="imgUrl" alt="imagem jogo">
  <footer>
    <div class="footer-year">
      <p>Ano:</p>
        <span>{{year}}</span>
    </div>
    <p>{{shortDescription}} </p>
    </footer>
</article>

 
</template>

<style scoped> 
header {
  display: flex;
  width: 100vw;
  align-items: flex-start;
  justify-content: start;
}

article {
  display: flex;
  flex-direction: column;
  /* align-items: center; */
  /* justify-content: center; */
  width: 300px;

}
footer .footer-year{
  display: flex;
  flex-direction: row;
  gap: 10px;
}


</style>