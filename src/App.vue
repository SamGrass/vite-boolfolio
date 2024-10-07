<script >
import Header from './components/Header.vue';

  export default {
    components: {
      Header,
    }
  }
</script>

<template>
  <div class="container">
    <div class="card">
      <Header />
      <router-view></router-view>
    </div>
  </div>
</template>

<style lang="scss" scoped>

</style>
