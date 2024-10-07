<script >
import Navbar from './views/components/Navbar.vue';

  export default {
    components: {
      Navbar,
    }
  }
</script>

<template>
  
  <div class="container">
    <div>
      <h1>BOOLFOLIO FRONT</h1>
      <div class="card">
        <Navbar />
        <router-view></router-view>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
h1 {
  margin-bottom: 2rem;
  text-align: center;
}
</style>
