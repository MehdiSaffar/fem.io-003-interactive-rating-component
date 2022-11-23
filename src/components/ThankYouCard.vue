
<script setup>
defineProps({
    rating: Number
})
</script>


<template>
    <article class="card">
        <img class="card__img" src="../../images/illustration-thank-you.svg"
            alt="Thank you illustration" />
        <p class="card__selection">You selected {{ rating }} out of 5</p>
        <h2 class="card__title">Thank you!</h2>
        <p>
            We appreciate you taking the time to give a rating. If you
            ever need more support, don’t
            hesitate to get in touch!
        </p>
    </article>
</template>

<style scoped lang="scss">
.card {
    justify-items: center;
    text-align: center;

    &__selection {
        color: var(--clr-primary-500);
        padding: 0.5rem 1rem ;
        line-height: 1;

        border-radius: 99999vmax;
        background-color: var(--clr-neutral-700);
    }
}
</style>