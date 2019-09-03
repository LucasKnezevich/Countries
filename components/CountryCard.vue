<script>
export default {
  props: {
    country: Object,
    required: true
  }
}
</script>

<template>
  <div class="card-wrapper">
    <section class="card">
      <img :src="country.flag" :alt="country.name" class="card__img">
      <h2 class="card__title mt-4">{{country.name}}</h2>
      <b-collapse id="collapse-1" class="mt-2">
        <p class="card__subregion"><span class="info-title">Subregion:</span>  {{country.subregion}}</p>
        <p class="card__capital"><span class="info-title">Capital:</span>  {{country.capital}}</p>
        <p class="card__population"><span class="info-title">Population:</span> {{country.population | Number(num).toLocaleString()}}</p>
      </b-collapse>
    </section>
  </div>
</template>

<style lang="scss">

.card {
  margin: 1rem;
  padding: 1rem;
  width: 220px;
  min-height: 300px;
  border: 2px solid #000000;
  background-color: rgba(255, 255, 255, .8);
  display: flex;
  &__img {
    display: block;
    max-width: 150px;
    // padding: 1px;
    border: 1px solid #000000;
    align-self: center;
  }
}

.info-title {
  font-weight: bold;
}

</style>