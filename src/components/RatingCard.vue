
<script setup>
const emit = defineEmits(['onRate'])

function onSubmit(e) {
    const data =  new FormData(e.target)
    const rating = +data.get('rating')
    emit('onRate', rating)
}

</script>

<template>
    <article class="card">
        <form @submit.prevent="onSubmit">
            <div class="card__decoration"></div>
            <h2 class="card__title">How did we do?</h2>
            <p>
                Please let us know how we did with your support request. All
                feedback is appreciated to help us
                improve our offering!
            </p>
            <fieldset class="card__ratings">
                <div class="card__rating" v-for="rating in [1, 2, 3, 4, 5]"
                    :key="rating">
                    <input type="radio" :id="`rating_${rating}`" name="rating"
                        :value="rating" />
                    <label :for="`rating_${rating}`">{{ rating }}</label>
                </div>
            </fieldset>
            <button type="submit" class="card__button">Submit</button>
        </form>
    </article>
</template>

<style scoped lang="scss">
.card {
    form {
        display: contents;
    }

    &__decoration {
        justify-self: start;
        border-radius: 50%;
        padding: 1rem;
        background-color: var(--clr-neutral-700);

        &::before {
            content: url('../assets/images/icon-star.svg');
            display: block;
            width: 1rem;
            height: 1rem;
        }
    }

    &__button {
        background-color: var(--clr-primary-500);
        color: var(--clr-neutral-100);
        border: none;
        padding: 0.6rem;
        border-radius: 99999vmax;
        text-transform: uppercase;
        letter-spacing: 0.2ch;
        font-weight: var(--fw-bold);
        cursor: pointer;
        transition: background-color 250ms ease;

        &:is(:hover, :focus) {
            background-color: var(--clr-neutral-100);
            color: var(--clr-primary-500);
        }
    }

    &__ratings {
        display: flex;
        justify-content: space-between;
        gap: 0.5rem;
        flex-wrap: nowrap;
        border: none;
        padding: 0;
        // margin-block: 0.3rem;

        .card__rating {
            display: grid;
            place-items: center;

            background-color: var(--clr-neutral-700);
            transition: background-color 250ms ease;

            border-radius: 50%;


            width: 3.5rem;
            aspect-ratio: 1;

            &:has(label:is(:hover, :focus)) {
                background-color: var(--clr-primary-500);
                color: var(--clr-neutral-100);
            }

            &:has(input:checked) {
                background-color: var(--clr-neutral-500);
                color: var(--clr-neutral-100);
            }

            &>* {
                grid-row: 1;
                grid-column: 1;
                width: 100%;
                height: 100%;
            }

            input {
                appearance: none;
            }

            label {
                display: grid;
                place-content: center;
                cursor: pointer;
            }
        }
    }
}
</style>