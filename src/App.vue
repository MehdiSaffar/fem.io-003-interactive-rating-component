<script setup>

  // <!-- Thank you state start -->

  // You selected
  // <!-- Add rating here -->
  // out of 5 Thank you! We appreciate you taking the time to give a rating. If you
  // ever need more support, don’t
  // hesitate to get in touch!

  // <!-- Thank you state end -->
</script>


<template>
  <main>
    <article class="card">
      <form>
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
            <input type="radio" :id="`rating_${rating}`" name="rating" :value="rating" />
            <label :for="`rating_${rating}`">{{ rating }}</label>
          </div>
        </fieldset>
        <button type="submit" class="card__button">Submit</button>
      </form>
    </article>
  </main>
</template>
