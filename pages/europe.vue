<template>
  <div class="container">
    <Header v-slot:title>{{title[1]}}</Header>

    <div class="button-wrapper">
      <b-button v-b-toggle.collapse-1 class="toggle-button" variant="primary">Toggle additional info</b-button>
    </div>

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
import Header from '@/components/Header'

export default {
  components: {
    CountryCard,
    Header
  },
  data () {
    return {
      loading: true,
      countries: null,
      errored: false,
      title: ['Europe | Countries', 'Europe']
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
      title: this.title[0],
      meta: [
        {hid: 'description', name: 'description', content: 'Countries of Europe'}
      ]
    }
  } 
}
</script>