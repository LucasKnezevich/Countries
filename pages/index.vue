<template>
  <div class="container mt-5">
    <!-- Jumbotron -->
    <b-jumbotron bg-variant="info" text-variant="white" border-variant="dark">
      <template slot="header">Countries</template>
      <template slot="lead">
      This website contains information about countries, grouped by region.
      </template>
      <hr class="my-4">
      <p>All data provided by the <a href="http://restcountries.eu" target="_blank">restcountries.eu</a> API.</p>
    </b-jumbotron>
    
    <!-- Flag carousel -->
    <Flags />

  </div>
</template>

<script>
import axios from 'axios'
import Flags from '@/components/Flags.vue'


export default {
  components: {
    Flags
  },
  data () {
    return {
      loading: true,
      countries: null,
      errored: false
    }
  },
  mounted () {
    axios
      .get('https://restcountries.eu/rest/v2/all')
      .then(response => (this.countries = response.data))
      .catch(error => {
        console.log(error)
        this.errored = true 
      })
      .finally(() => this.loading = false)
  }
}
</script>


<style lang="scss" scoped>

a {
  text-decoration: none;
  color: #8b3cb9;
}

</style>
