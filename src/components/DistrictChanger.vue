<script setup>
import {ref, reactive} from 'vue'
const location  = reactive({
    city: 'Dhaka',
    weather:'Sunny'
})

const setLocation = function(newLocation, newWeather){
    location.city = newLocation
    location.weather = newWeather
}

</script>

<template>
  <section class="container mx-auto flex items-center flex-col">
        <h1 class="text-center text-2xl py-10">Events & Reactivity in Vue.js</h1>
        <div class="container mx-auto flex space-x-5 justify-center m-5">
            <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded" @click="setLocation('Dhaka','Sunny')">
                Dhaka
            </button>
            <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded" @click="setLocation('Rajshahi','Partly Cloudy')">
                Rajshahi
            </button>
            <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded" @click="setLocation('Khulna', 'Thunderstorm')">
                Khulna
            </button>
        </div>
        <div class="w-1/3 bg-gray-200 p-10 flex items-center flex-col space-y-10">
            <h1 class="text-3xl">{{ location.city }}</h1>
            <h2 class="text-2xl">Weather: {{ location.weather }}</h2>
            <img src="https://creazilla-store.fra1.digitaloceanspaces.com/icons/7911203/weather-icon-md.png" alt="">
            <img src="https://creazilla-store.fra1.digitaloceanspaces.com/icons/7912718/weather-icon-md.png" alt="">
            <img src="https://creazilla-store.fra1.digitaloceanspaces.com/icons/7913380/weather-icon-md.png" alt="">
            <img src="https://creazilla-store.fra1.digitaloceanspaces.com/icons/7912589/weather-icon-md.png" alt="">
        </div>
    </section>
</template>

<style scoped></style>