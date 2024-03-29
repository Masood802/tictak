<script setup>
import { ref } from 'vue';
let currentPlayer=ref('X')
let winner=ref('')
function Playnext(id){
  const sqaur=document.getElementById(id)
  sqaur.innerText=currentPlayer.value;
  sqaur.classList.add("disabled");
  currentPlayer.value=currentPlayer.value==='X'?'O':'X'
  checkwin();
}
function checkwin(){
  if(document.getElementById('1').innerText==='X'&& 
  document.getElementById('2').innerHTML==='X' && 
  document.getElementById('3').innerText==='X' ){
    winner.value='X'
    document.getElementById('winner').style.display="block";
   
  }
  
}
function reset(){
  
  for(let i=1; i<=9;i++){
    document.getElementById(i).innerText=''
  }
   document.getElementById('winner').style.display="none";
   
  
}
</script>

<template>
  <div class="  flex justify-center items-center flex-col  w-screen h-[450px] relative">
    <p class="text-3xl m-4">Game Board</p>
    <h2 class="text-2xl m-4 font-bold text-red-950">Current Player "{{ currentPlayer }}"</h2>
    <div class="flex">
    <div class="block hover:bg-lime-600" id="1" @click="Playnext('1')"></div>
    <div class="block hover:bg-lime-600" id="2" @click="Playnext('2')"></div>
    <div class="block hover:bg-lime-600" id="3" @click="Playnext('3')"></div>
    </div>
    <div class="flex">
    <div class="block hover:bg-lime-600" id="4" @click="Playnext('4')"></div>
    <div class="block hover:bg-lime-600" id="5" @click="Playnext('5')"></div>
    <div class="block hover:bg-lime-600" id="6" @click="Playnext('6')"></div>
    </div>
    <div class="flex">
    <div class="block hover:bg-lime-600" id="7" @click="Playnext('7')"></div>
    <div class="block hover:bg-lime-600" id="8" @click="Playnext('8')"></div>
    <div class="block hover:bg-lime-600" id="9" @click="Playnext('9')"></div>
    </div>
    <p class="absolute top-[35%] text-3xl text-green-800 font-bold hidden bg-yellow-600 px-4 py-20 w-52 h-52 text-center" id="winner"  >Winner is {{ winner }}</p>
    <button class="bg-red-600 w-32 h-10 rounded-md text-white my-3 py-2" @click="reset">Reset</button>
  </div>
</template>
