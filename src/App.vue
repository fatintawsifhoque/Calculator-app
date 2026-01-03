<template>
  <section class="h-screen w-screen bg-[#3B4664] flex flex-col justify-center items-center" :class="sTheme == 2 ? 'bg-[#E6E6E6]' : sTheme == 3 ? 'bg-[#17062A]' :''">
    <!-- Title & Theme -->
   <div class="w-81.25 md:w-135 mb-9 flex justify-between">
    <h1 class="font-bold  text-2xl " :class="sTheme == 1 ? 'text-white' : sTheme==2? 'text-[#33342D]' : sTheme == 3 ? 'text-[#FEDF3F]' :''">Calc</h1>
    <div class=" flex gap-2.5">
      <p class=" font-bold text-lg" :class="sTheme == 1 ? 'text-white' : sTheme==2? 'text-[#33342D]' : sTheme == 3 ? 'text-[#FEDF3F]' :''">Theme</p>
      <button class="w-10 rounded-lg border cursor-pointer border-amber-100" @click="sTheme ='1'" :class="sTheme == 1 ? 'bg-[#D43D31] text-white' : sTheme==2? 'bg-[#D3CDCD] text-[#33342D]' : sTheme == 3 ? 'bg-[#1E0836] text-[#FEDF3F]' :''">1</button>
      <button class="w-10 rounded-lg border cursor-pointer border-amber-100" @click="sTheme ='2'" :class="sTheme == 1 ? 'bg-[#252D44] text-white' : sTheme==2? 'bg-[#C45907] text-[white]' : sTheme == 3 ? 'bg-[#1E0836] text-[#FEDF3F]' :''">2</button>
      <button class="w-10 rounded-lg border cursor-pointer border-amber-100" @click="sTheme ='3'" :class="sTheme == 1 ? 'bg-[#252D44] text-white' : sTheme==2? 'bg-[#D3CDCD] text-[#33342D]' : sTheme == 3 ? 'bg-[#8EFFFC] text-black' :''">3</button>
      
    </div>
   </div>

   <!-- Display -->
    <div class="w-81.25 md:w-135 h-22.5 md:h-31.25  rounded-2xl  font-bold text-4xl pr-3 flex items-center justify-end mb-6 overflow-hidden" :class="sTheme == 1 ? 'bg-[#181F32] text-white' : sTheme==2? 'bg-[#EEEEEE] text-[#363530]' : sTheme == 3 ? 'text-[#FEDF3F] bg-[#1E0836]' :''">
      {{display}}
    </div>

    <!-- Keyboard -->
     <div class="w-81.25 md:w-135 h-105 rounded-2xl p-7 box-border" :class="sTheme == 1 ? 'bg-[#252D44]' : sTheme==2? 'bg-[#D3CDCD]' : sTheme == 3 ? 'bg-[#1E0836]' :''">

        <div class="h-18.75 w-full flex justify-between ">
          <button class="h-14.25 w-14.25 md:w-25.5  rounded-xl border-b-4  font-bold text-2xl  cursor-pointer" @click="capture(7)" :class="sTheme == 1 ? 'bg-[#EAE3DB] border-[#AFA4A2] text-[#424B54] hover:bg-[#FFFFFF]' : sTheme==2? 'bg-[#E5E4E0] border-[#A69C92] text-[#36362D] hover:bg-[#FFFFFF]' : sTheme == 3 ? 'bg-[#331B4D] border-[#77248D] text-[#FEDF3F] hover:bg-[#6B34AC]' :''">
            7
          </button>
          <button class="h-14.25 w-14.25 md:w-25.5 rounded-xl border-b-4 font-bold text-2xl cursor-pointer"
          @click="capture(8)" :class="sTheme == 1 ? 'bg-[#EAE3DB] border-[#AFA4A2] text-[#424B54] hover:bg-[#FFFFFF]' : sTheme==2? 'bg-[#E5E4E0] border-[#A69C92] text-[#36362D] hover:bg-[#FFFFFF]' : sTheme == 3 ? 'bg-[#331B4D] border-[#77248D] text-[#FEDF3F] hover:bg-[#6B34AC]' :''">
            8
          </button>
          <button class="h-14.25 w-14.25 md:w-25.5 rounded-xl border-b-4 font-bold text-2xl cursor-pointer" @click="capture(9)" :class="sTheme == 1 ? 'bg-[#EAE3DB] border-[#AFA4A2] text-[#424B54] hover:bg-[#FFFFFF]' : sTheme==2? 'bg-[#E5E4E0] border-[#A69C92] text-[#36362D] hover:bg-[#FFFFFF]' : sTheme == 3 ? 'bg-[#331B4D] border-[#77248D] text-[#FEDF3F] hover:bg-[#6B34AC]' :''">
            9
          </button>
          <button class="h-14.25 w-14.25 md:w-25.5  rounded-xl border-b-4  font-bold text-2xl  cursor-pointer"
          @click = "del" :class="sTheme == 1 ? 'bg-[#3B4664] border-[#414E71] text-white hover:bg-[#A3B2E2]' : sTheme==2? 'bg-[#38818A] border-[#1D5C65] text-white hover:bg-[#65B3BD]' : sTheme == 3 ? 'bg-[#56077A] border-[#BF16F5] text-white hover:bg-[#8731AE]' :''">
            DEL
          </button>
        </div>

        <div class="h-18.75 w-full flex justify-between ">
          <button class="h-14.25 w-14.25 md:w-25.5 rounded-xl border-b-4 font-bold text-2xl cursor-pointer" @click="capture(4)" :class="sTheme == 1 ? 'bg-[#EAE3DB] border-[#AFA4A2] text-[#424B54] hover:bg-[#FFFFFF]' : sTheme==2? 'bg-[#E5E4E0] border-[#A69C92] text-[#36362D] hover:bg-[#FFFFFF]' : sTheme == 3 ? 'bg-[#331B4D] border-[#77248D] text-[#FEDF3F] hover:bg-[#6B34AC]' :''">4</button>
          <button class="h-14.25 w-14.25 md:w-25.5 rounded-xl border-b-4 font-bold text-2xl cursor-pointer" @click="capture(5)" :class="sTheme == 1 ? 'bg-[#EAE3DB] border-[#AFA4A2] text-[#424B54] hover:bg-[#FFFFFF]' : sTheme==2? 'bg-[#E5E4E0] border-[#A69C92] text-[#36362D] hover:bg-[#FFFFFF]' : sTheme == 3 ? 'bg-[#331B4D] border-[#77248D] text-[#FEDF3F] hover:bg-[#6B34AC]' :''">5</button>
          <button class="h-14.25 w-14.25 md:w-25.5  rounded-xl border-b-4 font-bold text-2xl  cursor-pointer" @click="capture(6)" :class="sTheme == 1 ? 'bg-[#EAE3DB] border-[#AFA4A2] text-[#424B54] hover:bg-[#FFFFFF]' : sTheme==2? 'bg-[#E5E4E0] border-[#A69C92] text-[#36362D] hover:bg-[#FFFFFF]' : sTheme == 3 ? 'bg-[#331B4D] border-[#77248D] text-[#FEDF3F] hover:bg-[#6B34AC]' :''">6</button>
          <button class="h-14.25 w-14.25 md:w-25.5  rounded-xl border-b-4  font-bold text-2xl  cursor-pointer" @click="capture('+')" :class="sTheme == 1 ? 'bg-[#EAE3DB] border-[#AFA4A2] text-[#424B54] hover:bg-[#FFFFFF]' : sTheme==2? 'bg-[#E5E4E0] border-[#A69C92] text-[#36362D] hover:bg-[#FFFFFF]' : sTheme == 3 ? 'bg-[#331B4D] border-[#77248D] text-[#FEDF3F] hover:bg-[#6B34AC]' :''">+</button>
        </div>

        <div class="h-18.75 w-full flex justify-between ">
          <button class="h-14.25 w-14.25 md:w-25.5  rounded-xl border-b-4  font-bold text-2xl  cursor-pointer" @click="capture(1)" :class="sTheme == 1 ? 'bg-[#EAE3DB] border-[#AFA4A2] text-[#424B54] hover:bg-[#FFFFFF]' : sTheme==2? 'bg-[#E5E4E0] border-[#A69C92] text-[#36362D] hover:bg-[#FFFFFF]' : sTheme == 3 ? 'bg-[#331B4D] border-[#77248D] text-[#FEDF3F] hover:bg-[#6B34AC]' :''">1</button>
          <button class="h-14.25 w-14.25 md:w-25.5  rounded-xl border-b-4  font-bold text-2xl  cursor-pointer" @click="capture(2)" :class="sTheme == 1 ? 'bg-[#EAE3DB] border-[#AFA4A2] text-[#424B54] hover:bg-[#FFFFFF]' : sTheme==2? 'bg-[#E5E4E0] border-[#A69C92] text-[#36362D] hover:bg-[#FFFFFF]' : sTheme == 3 ? 'bg-[#331B4D] border-[#77248D] text-[#FEDF3F] hover:bg-[#6B34AC]' :''">2</button>
          <button class="h-14.25 w-14.25 md:w-25.5  rounded-xl border-b-4 font-bold text-2xl cursor-pointer" @click="capture(3)" :class="sTheme == 1 ? 'bg-[#EAE3DB] border-[#AFA4A2] text-[#424B54] hover:bg-[#FFFFFF]' : sTheme==2? 'bg-[#E5E4E0] border-[#A69C92] text-[#36362D] hover:bg-[#FFFFFF]' : sTheme == 3 ? 'bg-[#331B4D] border-[#77248D] text-[#FEDF3F] hover:bg-[#6B34AC]' :''">3</button>
          <button class="h-14.25 w-14.25 md:w-25.5  rounded-xl border-b-4  font-bold text-2xl cursor-pointer" @click="capture('-')" :class="sTheme == 1 ? 'bg-[#EAE3DB] border-[#AFA4A2] text-[#424B54] hover:bg-[#FFFFFF]' : sTheme==2? 'bg-[#E5E4E0] border-[#A69C92] text-[#36362D] hover:bg-[#FFFFFF]' : sTheme == 3 ? 'bg-[#331B4D] border-[#77248D] text-[#FEDF3F] hover:bg-[#6B34AC]' :''">-</button>
        </div>

        <div class="h-18.75 w-full flex justify-between ">
          <button class="h-14.25 w-14.25 md:w-25.5  rounded-xl border-b-4  font-bold text-2xl cursor-pointer" @click="capture('.')" :class="sTheme == 1 ? 'bg-[#EAE3DB] border-[#AFA4A2] text-[#424B54] hover:bg-[#FFFFFF]' : sTheme==2? 'bg-[#E5E4E0] border-[#A69C92] text-[#36362D] hover:bg-[#FFFFFF]' : sTheme == 3 ? 'bg-[#331B4D] border-[#77248D] text-[#FEDF3F] hover:bg-[#6B34AC]' :''">.</button>
          <button class="h-14.25 w-14.25 md:w-25.5  rounded-xl border-b-4 font-bold text-2xl  cursor-pointer" @click="capture(0)" :class="sTheme == 1 ? 'bg-[#EAE3DB] border-[#AFA4A2] text-[#424B54] hover:bg-[#FFFFFF]' : sTheme==2? 'bg-[#E5E4E0] border-[#A69C92] text-[#36362D] hover:bg-[#FFFFFF]' : sTheme == 3 ? 'bg-[#331B4D] border-[#77248D] text-[#FEDF3F] hover:bg-[#6B34AC]' :''">0</button>
          <button class="h-14.25 w-14.25 md:w-25.5  rounded-xl border-b-4 font-bold text-2xl  cursor-pointer" @click="capture('/')" :class="sTheme == 1 ? 'bg-[#EAE3DB] border-[#AFA4A2] text-[#424B54] hover:bg-[#FFFFFF]' : sTheme==2? 'bg-[#E5E4E0] border-[#A69C92] text-[#36362D] hover:bg-[#FFFFFF]' : sTheme == 3 ? 'bg-[#331B4D] border-[#77248D] text-[#FEDF3F] hover:bg-[#6B34AC]' :''">/</button>
          <button class="h-14.25 w-14.25 md:w-25.5  rounded-xl border-b-4 font-bold text-2xl cursor-pointer" @click="capture('*')" :class="sTheme == 1 ? 'bg-[#EAE3DB] border-[#AFA4A2] text-[#424B54] hover:bg-[#FFFFFF]' : sTheme==2? 'bg-[#E5E4E0] border-[#A69C92] text-[#36362D] hover:bg-[#FFFFFF]' : sTheme == 3 ? 'bg-[#331B4D] border-[#77248D] text-[#FEDF3F] hover:bg-[#6B34AC]' :''">X</button>
        </div>

        <div class="h-18.75 w-full flex justify-between ">
          <button class="h-14.25 w-32 md:w-57 rounded-xl border-b-4 font-bold text-2xl cursor-pointer" @click="reset" :class="sTheme == 1 ? 'bg-[#3B4664] border-[#414E71] text-white hover:bg-[#A3B2E2]' : sTheme==2? 'bg-[#38818A] border-[#1D5C65] text-white hover:bg-[#65B3BD]' : sTheme == 3 ? 'bg-[#56077A] border-[#BF16F5] text-white hover:bg-[#8731AE]' :''">RESET</button>
    <button class="h-14.25 w-32 md:w-57  rounded-xl border-b-4  font-bold text-2xl  cursor-pointer" @click="calculate" :class="sTheme == 1 ? 'bg-[#D13F30] border-[#7A2B27] text-white hover:bg-[#F96C5B]' : sTheme==2? 'bg-[#C85401] border-[#863700] text-white hover:bg-[#FF8B38]' : sTheme == 3 ? 'bg-[#00DECF] border-[#6EFAF1] text-black hover:bg-[#94FFF9]' :''">=</button>
        </div>

        
     </div>
  </section>
</template>

<script setup>
import { ref } from 'vue';

const sTheme = ref('1')
const display = ref('0')
const capture = (value) => {
    if (display.value === '0') {
    display.value = ''
  }
  display.value += value
}
const del = () => {
  if (display.value.length === 1) {
    display.value = '0'
  } else {
    display.value = display.value.slice(0, -1)
  }
}

const reset = () => {
  display.value = '0'
}

const calculate = () => {
  try {
    display.value = eval(display.value)
  }
  catch (error) {
    display.value = "Error"
  }
}
</script>

<style scoped>
</style>