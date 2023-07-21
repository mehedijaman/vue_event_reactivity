<script setup>
import {ref} from 'vue'
const location  = ref('Dhaka');

const setLocation = function(newLocation){
    location.value = newLocation
}

const buttonColor = ref('bg-purple-500')

</script>

<template>
  <section class="container mx-auto flex items-center flex-col">
        <h1 class="text-center text-2xl py-10">Events & Reactivity in Vue.js</h1>
        <div class="container mx-auto flex space-x-5 justify-center m-5">
            <button :class="buttonColor" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded" @click="setLocation('Dhaka')">
                Dhaka
            </button>
            <button :class="buttonColor" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded" @click="setLocation('Rajshahi')">
                Rajshahi
            </button>
            <button :class="buttonColor" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded" @click="setLocation('Khulna')">
                Khulna
            </button>
        </div>
        <h1 class="text-2xl m-10">Current Location is {{ location }}</h1>
        <div class="mt-10 flex space-x-5 justify-center">
            <div @click="buttonColor = 'bg-orange-500'" class="cursor-pointer w-10 h-10 bg-orange-500"></div>
            <div @click="buttonColor = 'bg-indigo-500'" class="cursor-pointer w-10 h-10 bg-indigo-500"></div>
            <div @click="buttonColor = 'bg-purple-500'" class="cursor-pointer w-10 h-10 bg-purple-500"></div>
        </div>
    </section>
</template>

<style scoped></style>