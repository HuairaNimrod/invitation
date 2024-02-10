<script setup>

import { ref } from "vue";

const isVisible = ref(true);
const isNotVisible = ref(false);


setTimeout(() => {
    isVisible.value = !isVisible.value;
    isNotVisible.value = !isNotVisible.value;
  }, 8000);
  



</script>

<template>
  
<div class="main">

  <div class="image_container">
    <img v-show="isVisible" alt="Vue logo" class="pulse" src="./assets/image.png" width="125" height="125" />
  </div>

  <div v-show="isNotVisible" class="grid-container">

    <div class="item-a">
      
        <img  class="ballon-1"  alt="boy ballon" src="./assets/boy_ballon.png" />
        <img  class="ballon-2"  alt="girl ballon" src="./assets/girl_ballon.png" />
      
    </div>

    <div class="item-b">
      <div class="text-invitation ">
        <p class="texty-in">Un pequeño bebé esta en camino</p>
        <p class="texty-in">Acompañanos en la revelacion</p>
        <p class="texty-in"> de género de nuestro bebé</p>
        <p class="texty-in special-font text-margin">Nim & Keyla</p>
        <p class="texty-in text-margin" >Sábado 17 de Febrero</p>
        <p class="texty-in">de 5:00 a 7:00 pm</p>
        <p class="texty-in text-margin">Club House Liberty Square</p>
        <p class="texty-in">556 N. 400 E. Provo, UT 84606</p>
      </div>  
    </div>

    <div class="item-c">
      <div>
        <h3>Team niña</h3>
        <img alt="diaper" src="./assets/diapers.png" />
        <p>pañales</p>
      </div>
      <div>
        <h3>Team niño</h3>
        <img alt="wipes" src="./assets/wipes.png" />
        <p>pañitos humedos</p>
      </div>  
    </div>
  </div>
  
</div>
  

  
</template>

<style scoped>

.main{
  color: #918484;
  position:absolute;
  top:0;
  left:0;
  bottom:0;
  right:0;
  background-color: #fff;
  animation-name: back;
  animation-duration: 8s;
}

@keyframes back {
  from{background-color: #918484;}
  to {background-color: white;}
}



.texty-in{
  color: #918484;
}
.pulse {
  animation: pulse 1s infinite ease-in-out alternate;
}
@keyframes pulse {
  from { transform: scale(0.8); }
  to { transform: scale(1.1); }
}

.image_container{
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100%;
}

.ballon-1{
  position: absolute;
  top: 80px;
  left: 0;
  width:120px ;
}
.ballon-2{
  position: absolute;
  top: 0px;
  left: 80px;
  width:120px ;
  z-index: -1;
}

.text-invitation{
  position: absolute;
  right: 0px;
  top: 30%;
}

.text-margin{
  margin-top: 15px;
}

.special-font{
  font-family: 'Courier New', Courier, monospace;
  font-size: 25px;
  letter-spacing: -2px;
}
@media (min-width: 1024px) {
  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}




</style>
