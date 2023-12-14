<script setup>
function insert(num) {
  let numero =document.getElementById('resultado').innerHTML;
  document.getElementById('resultado').innerHTML=numero+num;
  
}
function clean(){
  document.getElementById('resultado').innerHTML=""
}
function back(){
  let resultado=document.getElementById('resultado').innerHTML;
  document.getElementById('resultado').innerHTML=resultado.substring(0,resultado.length -1)
}
function calcular(){
  let resultado=document.getElementById('resultado').innerHTML;
  if(resultado){
    document.getElementById('resultado').innerHTML =eval(resultado);
  }
}
</script>

<template>
  <div class="fundo">
    <h1>Calculadora</h1>

    <div class="Calculadora">
      <p id="resultado"></p>
      <table>
        <tr>
          <td><button class="buttons" @click="clean('C')">C</button></td>
          <td><button class="buttons" @click="back('<')">B</button></td>
          <td><button class="buttons" @click="insert('/')">/</button></td>
          <td><button class="buttons" @click="insert('*')">X</button></td>
        </tr>
        <tr>
          <td><button class="buttons" @click="insert('7')">7</button></td>
          <td><button class="buttons" @click="insert('8')">8</button></td>
          <td><button class="buttons" @click="insert('9')">9</button></td>
          <td><button class="buttons" @click="insert('-')">-</button></td>
        </tr>
        <tr>
          <td><button class="buttons" @click="insert('4')">4</button></td>
          <td><button class="buttons" @click="insert('5')">5</button></td>
          <td><button class="buttons" @click="insert('6')">6</button></td>
          <td><button class="buttons" @click="insert('+')">+</button></td>
        </tr>
        <tr>
          <td><button class="buttons" @click="insert('1')">1</button></td>
          <td><button class="buttons" @click="insert('2')">2</button></td>
          <td><button class="buttons" @click="insert('3')">3</button></td>
          <td rowspan="2">
            <button class="buttons" style="height: 100px" @click="calcular('=')">=</button>
          </td>
        </tr>
        <tr>
          <td colspan="2">
            <button class="buttons" style="width: 106px" @click="insert('0')">0</button>
          </td>
          <td><button class="buttons" @click="insert('.')">.</button></td>
        </tr>
      </table>
    </div>
  </div>
</template>

<style scoped>
* {
  margin: 0;
  padding: 0;
}
.fundo {
  background-image: linear-gradient(45deg, black, rgb(36, 230, 197));
  height: 100vh;
  color: white;
  text-align: center;
}
#resultado {
  color: black;
  height: 30px;
  width: 207px;
  background-color: aliceblue;
  margin: 5px;
  font-size: 25px;
  text-align: right;
  padding: 5px;
}
.Calculadora {
  position: absolute;
  background-color: black;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  border-radius: 15px;
  padding: 15px;
  opacity: 0.8;
}
.buttons {
  border-radius: 25px;
  width: 50px;
  height: 50px;
  font-size: 25px;
  cursor: pointer;
  background-color: rgb(31, 31, 31);
  border: none;
  color: rgb(224, 9, 9);
  margin: 3px;
}
.buttons:hover {
  background-color: black;
  color: rgb(240, 240, 235);

  border: solid 1px rgb(255, 255, 255);
}
</style>
