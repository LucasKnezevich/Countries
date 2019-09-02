

<template>
  <div class="container">
    <h1 class="page-title text-center">The Americas</h1>
    
    <section class="card-wrap">
      <CountryCard
        v-for="country in countries"
        :key="country.id"
        :country="country"
      />
    </section>
  </div>
</template>

<script>
import axios from 'axios'
import CountryCard from '@/components/CountryCard.vue'

export default {
  components: {
    CountryCard
  },
  data () {
    return {
      loading: true,
      countries: null,
      errored: false,
      title: 'The Americas | Countries'
    }
  },
  mounted () {
    axios
      .get('https://restcountries.eu/rest/v2/region/americas')
      .then(response => (this.countries = response.data))
      .catch(error => {
        console.log(error)
        this.errored = true 
      })
      .finally(() => this.loading = false)
  },
  head () {
    return {
      title: this.title,
      meta: [
        {hid: 'description', name: 'descriptoon', content: 'Countries of The Americas'}
      ]
    }
  } 
}
</script>

<style lang="scss" scoped>

// .card-wrap {
//   display: grid;
//   grid-template-columns: repeat(2, 1fr);
// }

</style>