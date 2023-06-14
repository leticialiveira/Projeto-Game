<script setup>
defineProps({
        title: String,
        imgUrl:String,
        year: Number,
        shortDescription: String
    })

 
</script>

<template>
<article>
  <div class="main">

    <div class="header">
      <h1>{{title}}</h1>
  </div>
  <img :src="imgUrl" alt="imagem jogo">
  <footer>
    <div class="footer-year">
      <span>Ano:</span>
      <span>{{year}}</span>
    </div>
    <p>{{shortDescription}} </p>
  </footer>
</div>
</article>

 
</template>

<style scoped> 

article {
  display: flex;
  flex-direction: column;
  width: 300px;
}
.main{
  position: relative;
  padding: 20px;
}
.main img {
  box-shadow: 5px 5px 20px black;
}
.main:hover{
  top:-2px;
  box-shadow: 5px 5px 20px  rgba(36,122,139,1) ;
}
.header {
  display: flex;
  width: 100vw;
  align-items: flex-start;
  justify-content: start;
}

.header h1 {
  color: #D1F2EB ;
}

footer .footer-year{
  display: flex;
  flex-direction: row;
  gap: 10px;
  text-decoration: underline #ABB2B9;
}

footer p {
  color: #D7BDE2;
}

</style>