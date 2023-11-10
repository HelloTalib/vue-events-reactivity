
<template>
  <section class="container mx-auto flex items-center flex-col">
        <h1 class="text-center text-2xl py-10">Events & Reactivity in Vue.js</h1>
        <div class="container mx-auto flex space-x-5 justify-center m-5">
            <button style="display: inline-block;" class=" bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded" @click=" getCurrentLocation(division);" v-for="division in bangladeshDivisions" :key="division">
                {{division}}
            </button>
        </div>
        <h1 class="text-2xl m-10">Current Location is {{location}}</h1>
    </section>
</template>

<script setup>
import { ref } from 'vue';
const location = ref('Dhaka');

const bangladeshDivisions = [
    "Dhaka",
    "Chittagong",
    "Rajshahi",
    "Khulna",
    "Barisal",
    "Sylhet",
    "Rangpur",
    "Mymensingh"
];

console.log(bangladeshDivisions);



const getCurrentLocation = (newLocation) => {
    location.value = newLocation;
}
</script>
<style scoped></style>