<script setup>
import {ref, reactive} from 'vue'
const activeIndex = ref('0')

const accordions = reactive([
    {
        title: 'When to use Accordion Components?',
        content: 'Lorem ipsum dolor sit, amet consectetur adipisicing elit. Sequi dolor dolorum odio, saepe quibusdam iusto possimus nesciunt dolores assumenda quae totam, doloremque odit. Itaque cum animi, labore debitis deserunt iusto!',
        isOpen: 1
    },
    {
        title: 'When to use Accordion Components?',
        content: 'Lorem, ipsum dolor sit amet consectetur adipisicing elit. Ut suscipit itaque, sequi incidunt ab sit optio debitis dignissimos doloribus ratione nobis id mollitia maiores eveniet necessitatibus dolorum praesentium! Corrupti, at.',
        isOpen: 0
    },
    {
        title: 'When to use Accordion Components?',
        content: 'Lorem ipsum dolor sit, amet consectetur adipisicing elit. Sequi dolor dolorum odio, saepe quibusdam iusto possimus nesciunt dolores assumenda quae totam, doloremque odit. Itaque cum animi, labore debitis deserunt iusto!',
        isOpen: 0
    },
    {
        title: 'When to use Accordion Components?',
        content: 'Lorem, ipsum dolor sit amet consectetur adipisicing elit. Ut suscipit itaque, sequi incidunt ab sit optio debitis dignissimos doloribus ratione nobis id mollitia maiores eveniet necessitatibus dolorum praesentium! Corrupti, at.',
        isOpen: 0
    },
    {
        title: 'When to use Accordion Components?',
        content: 'Lorem ipsum dolor sit, amet consectetur adipisicing elit. Sequi dolor dolorum odio, saepe quibusdam iusto possimus nesciunt dolores assumenda quae totam, doloremque odit. Itaque cum animi, labore debitis deserunt iusto!',
        isOpen: 0
    },
    {
        title: 'When to use Accordion Components?',
        content: 'Lorem, ipsum dolor sit amet consectetur adipisicing elit. Ut suscipit itaque, sequi incidunt ab sit optio debitis dignissimos doloribus ratione nobis id mollitia maiores eveniet necessitatibus dolorum praesentium! Corrupti, at.',
        isOpen: 0
    }
])

</script>

<template>
   <section class="container mx-auto flex items-center flex-col">
      <h1 class="text-center text-2xl py-10">Vue Accordion</h1>
    
      <div class="p-10 bg-gradient-to-br from-pink-50 to-indigo-100 grid place-items-center">
        <div class="w-6/12 mx-auto rounded border">
          <div class="bg-white p-10 shadow-sm">
            <h3 class="text-lg font-medium text-gray-800">Several Windows stacked on each other</h3>
            <p class="text-sm font-light text-gray-600 my-3">
              The accordion is a graphical control element comprising a vertically stacked list of items such as labels or thumbnails
            </p>
  
            <div class="h-1 w-full mx-auto border-b my-5"></div>
  
            <!-- What is term -->
            <div class="transition hover:bg-indigo-50" v-for="(accordion, index) in accordions" :key="index">
              <!-- header -->
              <div @click="activeIndex = index" class="accordion-header cursor-pointer transition flex space-x-5 px-5 items-center h-16">
                <i class="fas" :class="index == activeIndex?'fa-minus':'fa-plus'"></i>
                <h3>{{ accordion.title }}</h3>
              </div>
              <!-- Content -->
              <div class="px-5 pt-0 text-left pb-5" v-show="index == activeIndex">
                <p class="leading-6 font-light pl-9 ">{{ accordion.content }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <div class="accordion" id="accordionExample">
      <div class="accordion-item" v-for="(accordion,index) in accordions" :key="index">
        <h2 class="accordion-header" id="headingOne">
          <button class="accordion-button" type="button" data-bs-toggle="collapse" data-bs-target="#collapseOne" aria-expanded="true" aria-controls="collapseOne">
            {{ accordion.title }}
          </button>
        </h2>
        <div @click="activeIndex = !accordion.isOpen" id="collapseOne" class="accordion-collapse collapse" :class="accordion.isOpen?'show':''" aria-labelledby="headingOne" data-bs-parent="#accordionExample">
          <div class="accordion-body">
            {{ accordion.content }}
          </div>
        </div>
      </div>
    </div>
</template>

<style scoped></style>