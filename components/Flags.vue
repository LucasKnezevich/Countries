<script>
import axios from 'axios'

export default {
    props: {
        
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


<template>
    <div class="carousel-wrapper">
        <b-carousel
            id="carousel-1"
            v-model="slide"
            :interval="4000"
            controls
            background="#ababab"
            img-width="1024"
            img-height="480"
            style="text-shadow: 1px 1px 2px #333;"
            @sliding-start="onSlideStart"
            @sliding-end="onSlideEnd"
        >
        <b-carousel-slide
            v-for="country in countries"
            :key="country.id"
            :caption="country.name"
            :img-src="country.flag">
        </b-carousel-slide>
    </b-carousel>
</div>
</template>

<style lang="scss" scoped>

    // .carousel-wrapper {
    //     max-height: 2rem;
    // }

</style>