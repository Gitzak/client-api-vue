<template>
  <Navbar />
  <div class="container mt-5">
    <vue-simple-spinner></vue-simple-spinner>
    <router-view/>
  </div>
</template>

<script>
import Navbar from './components/Navbar';
export default {
  components: {
    Navbar

  }
}
</script>

<style>

</style>
