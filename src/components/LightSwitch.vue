<script setup>
import {ref, reactive} from 'vue'

const onIcon = '//img.icons8.com/?size=512&id=12244&format=png'
const offIcon = '//img.icons8.com/?size=512&id=75&format=png'

const lights = reactive([
    {
        name: 'Light 1',
        status: 0,
        offIcon: offIcon,
        onIcon: onIcon
    },
    {
        name: 'Light 2',
        status: 0,
        offIcon: offIcon,
        onIcon: onIcon
    },
    {
        name: 'Light 3',
        status: 0,
        offIcon: offIcon,
        onIcon: onIcon
    }
])

const bgBlue = 'bg-blue-700'
const bgGray = 'bg-gray-700'
</script>

<template>
    <section class="container mx-auto flex items-center flex-col">
        <h1 class="text-center text-2xl py-10">Assignment</h1>
        <p class="p-5">Make These Buttons Work</p>
        <div class="flex justify-between space-x-6">
            <div class="p-10 border w-96 flex flex-col space-y-5">
                <button @click="light.status = !light.status" v-for="(light,index) in lights" :key="index" :class="light.status?bgBlue:bgGray" class="hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
                   {{ light.name }} {{ light.status?'ON':'OFF' }}
                </button>
            </div>
            <div class="p-10 border w-96 flex flex-col space-y-5">
                <img v-for="(light,index) in lights" :key="index" class="w-12" :src="light.status?light.onIcon:light.offIcon" alt="">
            </div>
        </div>
    </section>
</template>

<style scoped></style>