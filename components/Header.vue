<template>
  <div> 
    <h1 class="page-title display-4 text-center text-black mt-5">
      <!-- Slot with default/fallback text -->
      <slot name="title">Welcome!</slot>
    </h1>     
  </div>
</template>

<script>
export default {
  name: 'Header'
}
</script>


<style scoped>

.page-title {
    font-weight: bold;
}

</style>