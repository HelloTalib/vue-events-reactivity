<script setup>
import { ref } from 'vue'
const accordionIndex = ref(null)

// Function to toggle accordion index on click
const toggleAccordion = (index) => {
  accordionIndex.value = accordionIndex.value !== index ? index : null;
}
const accordions = [
  {
    title: 'What is term?',
    content: 'Lorem ipsum dolor sit, amet consectetur adipisicing elit. Sequi dolor dolorum odio, saepe quibusdam iusto possimus nesciunt dolores assumenda quae totam, doloremque odit. Itaque cum animi, labore debitis deserunt iusto!'
  },
  {
    title: 'When to use Accordion Components?',
    content: 'Lorem, ipsum dolor sit amet consectetur adipisicing elit. Ut suscipit itaque, sequi incidunt ab sit optio debitis dignissimos doloribus ratione nobis id mollitia maiores eveniet necessitatibus dolorum praesentium! Corrupti, at.'
  },
  {
    title: 'How can it be defined?',
    content: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Minima facilis labore voluptates provident nam, delectus suscipit nihil optio voluptate quae porro fugiat magni excepturi doloribus.'
  },
  {
    title: 'Chamber reached do he nothing be?',
    content: 'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Ullam minima maiores magni dolore qui architecto pariatur incidunt repellat quos hic? Eius, eveniet accusantium! Quisquam, quo. Vitae ipsum ad veritatis commodi quasi expedita!'
  }
];
</script>

<template>
      <section class="container mx-auto flex items-center flex-col">
          <h1 class="text-center text-2xl py-10">Events & Reactivity in Vue.js</h1>

          <div class="p-10 bg-gradient-to-br from-pink-50 to-indigo-100 grid place-items-center">
            <div class="w-6/12 mx-auto rounded border">
              <div class="bg-white p-10 shadow-sm">
                <h3 class="text-lg font-medium text-gray-800">Several Windows stacked on each other</h3>
                <p class="text-sm font-light text-gray-600 my-3">
                  The accordion is a graphical control element comprising a vertically stacked list of items such as labels or thumbnails
                </p>

                <div class="h-1 w-full mx-auto border-b my-5"></div>

                <!-- What is term -->
                <div class="transition hover:bg-indigo-50" v-for="(accordion, index) in accordions" :key="accordion.title">
                  <!-- header -->
                  <div class="accordion-header cursor-pointer transition flex space-x-5 px-5 items-center h-16" @click="toggleAccordion(index)">
                    <i class="fas" :class="accordionIndex !== index ? 'fa-plus': 'fa-minus'"></i>
                    <h3>{{accordion.title}}</h3>
                  </div>
                  <!-- Content -->
                  <div class="px-5 pt-0 text-left pb-5" v-if="accordionIndex == index">
                    <p class="leading-6 font-light pl-9 ">
                      {{ accordion.content  }}
                    </p>
                  </div>
                </div>
              </div>
            </div>
          </div>



        </section>
</template>

<style scoped></style>