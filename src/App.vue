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
</template>