<template>
  <div class="container mt-5">
    <b-navbar toggleable="md">
      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
      <b-collapse id="nav-collapse" is-nav>
        <b-nav class="navbar rounded">
          <b-nav-item><nuxt-link to="/">Home</nuxt-link></b-nav-item>
          <b-nav-item-dropdown class="navbar__dropdown" id="my-nav-dropdown" text="Select Region" toggle-class="nav-link-custom">
            <b-dropdown-item><nuxt-link to="/africa">Africa</nuxt-link></b-dropdown-item>
            <b-dropdown-item><nuxt-link to="/americas">Americas</nuxt-link></b-dropdown-item>
            <b-dropdown-item><nuxt-link to="/asia">Asia</nuxt-link></b-dropdown-item>
            <b-dropdown-item><nuxt-link to="/europe">Europe</nuxt-link></b-dropdown-item>
            <b-dropdown-item><nuxt-link to="/oceania">Oceania</nuxt-link></b-dropdown-item>
          </b-nav-item-dropdown>
        </b-nav>
      </b-collapse>
    </b-navbar>
  </div>
</template>


<script>
export default {
    
}
</script>


<style lang="scss" scoped>

.container {
  height: 5rem;
  // display: flex;
}
.navbar {
  background-color: rgba(255, 255, 255, .9);
  &__dropdown {
    background-color: rgba(255, 255, 255, .1);
  }
}

</style>