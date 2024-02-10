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
    <img v-show="isVisible" ref="baby" alt="Vue logo" class="pulse" src="./assets/image.png" width="125" height="125" />
  </div>

  <div v-show="isNotVisible" class="grid-container">

    <div class="item-a">
      
        <img  class="ballon-1" ref="baby" alt="boy ballon" src="./assets/boy_ballon.png" />
        <img  class="ballon-2" ref="baby" alt="girl ballon" src="./assets/girl_ballon.png" />
      
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
        <img  ref="baby" alt="girl ballon" src="./assets/diapers.png" />
        <p>pañales</p>
      </div>
      <div>
        <h3>Team niño</h3>
        <img  ref="baby" alt="girl ballon" src="./assets/wipes.png" />
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

@keyframes opa {
  from { opacity: 0; }
  to { opacity: 1; }
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

/* grid */
.grid-container{
  animation: opa 10s linear ;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: repeat(5, 1fr);
  grid-column-gap: 0px;
  grid-row-gap: 0px;

  width: 90%;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
.item-a{
  grid-column: 1 / span 2;
  grid-row: 1 / span 4;
}
.item-b{
  grid-column: 2 / span 2;
  grid-row: 1 / span 4;
  text-align: right;
}
.item-c{
  padding-top: 30px;
  grid-column: 1 / span 3;
  grid-row: 5 / span 1;
}

/* bottom info */
.item-c{
  display: flex;
  align-items: baseline ;
  justify-content: space-evenly;
}
.item-c > div > h3{
  font-size: 15px;
}
.item-c > div > p {
  font-family: 'Courier New', Courier, monospace;
  font-size: 15px;
  letter-spacing: -1px;
}
.item-c > div > img{
  height: 40px;
  margin: 8px 0px 4px 0px;
}
.item-c > div{
  text-align: center;
}
/* bottom info end */


</style>
