<template>
  <div>
    <Nav />
    <nuxt />
    <Footer />
  </div>
</template>

<script>
import Nav from '@/components/Nav.vue'
import Footer from '@/components/Footer.vue'

export default {
  components: {
    Nav,
    Footer
  },
  data () {
    return {
      title: 'Countries'
    }
  },
  head () {
    return {
      title: this.title,
      meta: [
        {hid: 'description', name: 'descriptoon', content: 'Countries'}
      ]
    }
  }
}
</script>

<style lang="scss">
html {
  font-family: 'Source Sans Pro', -apple-system, BlinkMacSystemFont, 'Segoe UI',
    Roboto, 'Helvetica Neue', Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
  
}

*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}

body {
  background: linear-gradient(rgba(255, 255, 255, .3), rgba(255, 255, 255, .3)), url('~static/images/earth-big.jpg') no-repeat fixed center;
  /* background: url('~static/images/earth-big.jpg') no-repeat center; */
  /* background-size: 160%; */
  height: 100%;
}

/* .container {
  margin: 0 5rem;
  padding: 0;
} */

.card-wrap {
  min-height: 100vh;
  max-width: 1200px;
  margin: auto;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  justify-items: center;
  align-items: start;
  text-align: center;
}

.button-wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}

</style>
