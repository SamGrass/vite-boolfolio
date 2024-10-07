<script>
import axios  from 'axios';
import { store } from '../store'
import Loading from './components/Loading.vue';

  export default {
    name: 'projects',
    components: {
      Loading
    },
    data() {
      return {
        projects: [],
        isLoading: false,
      }
    },
    methods: {
      getApi(){
        this.isLoading = true;
        axios.get(store.apiURL + 'projects')
        .then(res => {
          this.isLoading = false
          this.projects = res.data.projects.data;
          
        })
      }
    },
    mounted() {
      this.getApi();
    },
  }
</script>

<template>
  <h2>PROGETTI</h2>
  <ul v-if="!isLoading">
    <li v-for="project in projects">{{ project.name }}</li>
  </ul>
  <div v-else="isLoading"><Loading/></div>
</template>

<style lang="scss" scoped>
h2 {
  margin-bottom: 2rem;
}
</style>
