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
        isLoading: true,
        paginatorData: {
          current_page: 1,
          links: []
        }
      }
    },
    methods: {
      getApi(apiURL){
        
        axios.get(apiURL)
        .then(res => {
          this.isLoading = false
          this.projects = res.data.projects.data;
          this.paginatorData.current_page = res.data.projects.current_page
          this.paginatorData.links = res.data.projects.links
          console.log(this.paginatorData);
          
        })
        .catch( err => {
          console.log(err.message);
          
        })
      }
    },
    mounted() {
      this.getApi(store.apiURL + 'projects');
    },
  }
</script>

<template>
  <h2>PROGETTI</h2>
  <div v-if="isLoading"><Loading/></div>
  <div v-else>
    <ul>
      <li v-for="project in projects">{{ project.name }}</li>
    </ul>

    <div class="paginator">
      <button v-for="(link, index) in paginatorData.links" :key="index" v-html="link.label" :disabled="link.active || !link.url" @click="getApi(link.url)"></button>
    </div>
  </div>
</template>

<style lang="scss" scoped>
h2 {
  margin-bottom: 2rem;
}

.paginator {
  margin-top: 0.5rem;
  display: flex;
  gap: 0.2rem;  
  button {
    padding: 0 0.3rem;
  }
}
</style>
