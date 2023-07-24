<script setup>
import {ref} from 'vue'
import SimpleCounter from './components/SimpleCounter.vue'
import DistrictChanger from './components/DistrictChanger.vue'
import Accordion from './components/Accordion.vue'
import LightSwitch from './components/LightSwitch.vue'
import VForArrayComponent from './components/VForArrayComponent.vue'

let componentName = ref('')
</script>

<template>
    <nav class="navbar navbar-expand-lg bg-body-tertiary">
        <div class="container-fluid">
            <a class="navbar-brand" href="#">Vue Reactivity & Events</a>
            <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
            <div class="navbar-nav">
                <a @click="componentName = 'SimpleCounter'" class="nav-link" :class="SimpleCounter == componentName?'active':''"  href="#">SimpleCounter</a>
                <a @click="componentName = 'DistrictChanger'" class="nav-link" :class="DistrictChanger == componentName?'active':''" href="#">DistrictChanger</a>
                <a @click="componentName = 'Accordion'" class="nav-link" :class="Accordion == componentName?'active':''" href="#">Accordion</a>
                <a @click="componentName = 'LightSwitch'" class="nav-link" :class="LightSwitch == componentName?'active':''" href="#">Light Switch</a>
            </div>
            </div>
        </div>
    </nav>
    <div v-if="'SimpleCounter' == componentName">
        <SimpleCounter/>
    </div>
    <div v-if="'DistrictChanger' == componentName">
        <DistrictChanger/>
    </div>

    <div v-if="'Accordion' == componentName">
        <Accordion/>
    </div>

    <div v-if="'LightSwitch' == componentName">
        <LightSwitch/>
    </div>
    <!-- <VForArrayComponent/> -->
</template>

<style scoped></style>