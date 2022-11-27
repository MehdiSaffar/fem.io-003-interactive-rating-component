<script setup>
import { ref } from 'vue';
import RatingCard from './components/RatingCard.vue'
import ThankYouCard from './components/ThankYouCard.vue'

const rating = ref(null)

function handleRate(a) {
  rating.value = a
}
</script>



<template>
  <main>
    <RatingCard v-if="!rating" @on-rate="handleRate"/>
    <ThankYouCard v-else :rating="rating"/>
  </main>
  <div class="attribution">
    Challenge by <a href="https://www.frontendmentor.io?ref=challenge" target="_blank">Frontend Mentor</a>. 
    Coded by <a href="https://github.com/MehdiSaffar">Mehdi Saffar</a>.
  </div>
</template>