<script setup>
  import { ref } from 'vue';

  const Valor = ref(0);
  const Texto = ref("Generador de Solicitudes")

  const Aumentar = function() {
    Valor.value+= 1;
  }

  const Disminuir = function() {
    Valor.value-=1;

    if(Valor.value < 0) {
      Valor.value = 0;
    }
  }

</script>

<template>
  
  <h1>{{Texto}}</h1>

  <nav class="Profile">

    <span class="Notification" v-if="Valor > 0">{{ Valor }}</span>
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/b/bf/Big_Floppa_and_Justin_2_%28cropped%29.jpg/528px-Big_Floppa_and_Justin_2_%28cropped%29.jpg" alt="">
    <div class="Nav_Buttons">

      <span @click="Aumentar" class="Button Button_Plus">+</span>
      <span @click="Disminuir" class="Button Button_Minus">-</span>

    </div>

    <p v-show="Valor == 0">No subs µ😢</p>

  </nav>

  <input type="text" v-model="Texto">
  
</template>

<style scoped>

  input {
    display: block;
    margin: 0 auto; 
    padding: 10px 20px;
    text-align: center;
    border-radius: 5px;
    outline: none;
    border: solid 1px;
  }

  h1 {
    text-align: center;
  }
  .Profile {
    background: #bbb;
    padding: 10px 20px;
    color: #000;
    position: relative;
    border-radius: 10px;
    user-select: none;
    margin: 20px 0;
  }
  .Profile img {
    width: 300px;
    height: 300px;
    object-fit: cover;
    border-radius: 50%;
    box-shadow: 0 0 5px 10px rgba(99, 94, 94, 0.7);
    transition: all 0.4s;
  }
  .Profile .Notification {
    height: 100px;
    width: 100px;
    background: red;
    color: #fff;
    font-size: 30px;
    position: absolute;
    border-radius: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
    top: -70px;
    right: 0;
    box-shadow: 0 0 5px 2px;
    transition: display 2s;
  }
  
  .Profile p {
    text-align: center;
  }

  .Profile .Nav_Buttons {
    width: 100%;
    display: flex;
    justify-content: space-between;
    font-size: xx-large;
    margin: 20px 0;
  }

  .Profile .Nav_Buttons .Button {
    width: 80px;
    height: 80px;
    background: #ededed;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 10px;
    cursor: pointer;
    box-shadow: 0 0 10px 5px rgba(99, 94, 94, 0.7);
  }

  .Profile img:hover {
    box-shadow: 0 0 5px 10px rgba(28, 177, 9, 0.7);
  }
  
</style>
