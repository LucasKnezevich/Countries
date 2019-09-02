<template>
  <div class="container">
    <h1 class="text-center">Europe</h1>
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
      title: 'Europe | Countries'
    }
  },
  mounted () {
    axios
      .get('https://restcountries.eu/rest/v2/region/europe')
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
        {hid: 'description', name: 'descriptoon', content: 'Countries of Europe'}
      ]
    }
  } 
}
</script>