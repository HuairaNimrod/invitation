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

  <div v-show="isNotVisible" class="texty">
    <img  class="ballon-2" ref="baby" alt="girl ballon" src="./assets/girl_ballon.png" />
    <img  class="ballon-1" ref="baby" alt="girl ballon" src="./assets/boy_ballon.png" />
    <div class="text-invitation">
      <p class="texty-in">Join us</p>
      <p class="texty-in">for a gender reveal</p>
      <p class="texty-in">celebrating</p>
      <p class="texty-in special-font text-margin">Nim & Keyla</p>
      <p class="texty-in text-margin" >Saturday, February 17</p>
      <p class="texty-in">at 5:00 pm</p>
      <p class="texty-in text-margin">Club House Liberty Square</p>
      <p class="texty-in">556 N. 400 E. Provo, UT 84604</p>
    </div>
</div>
  
</div>
  

  
</template>

<style scoped>


.main{
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

.texty{
  text-align: right;
  animation: opa 10s linear ;
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
position: fixed;
left: 21px;
top: 345px;
width:120px ;
}
.ballon-2{
position: fixed;
left: 87px;
top: 240px;
width:120px ;
}

.text-invitation{
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-15%, -45%);
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
