<script >
import Header from './views/components/Header.vue';

  export default {
    components: {
      Header,
    }
  }
</script>

<template>
  
  <div class="container">
    <div>
      <h1>BOOLFOLIO FRONT</h1>
      <div class="card">
        <Header />
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
