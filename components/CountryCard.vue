<script>
export default {
  props: {
    country: Object 
  }
}
</script>

<template>
  <div class="card-wrapper">
    <section class="card">
      <img :src="country.flag" :alt="country.name" class="card__img">
      <h2 class="card__title">{{country.name}}</h2>
      <p class="card__subregion">{{country.subregion}}</p>
      <p class="card__population">Population: {{country.population}}</p>
    </section>
  </div>
</template>

<style lang="scss">

.card-wrapper {

}

.card {
  margin: 1rem;
  padding: 1rem;
  width: 220px;
  min-height: 380px;
  border: 2px solid #000000;
  display: flex;
  &__img {
    display: block;
    max-width: 150px;
    // padding: 1px;
    border: 1px solid #000000;
    align-self: center;
  }
}

</style>