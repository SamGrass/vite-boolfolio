<script>
export default {
    name: 'home'
  }
</script>

<template>
  <div>
    <ul>
        <li><router-link :to="{name: 'home'}">HOME</router-link></li>
        <li><router-link :to="{name: 'projects'}">PROGETTI</router-link></li>
    </ul>
  </div>
</template>

<style lang="scss" scoped>
ul {
    display: flex;
    justify-content: center;
    gap: 1rem;
    margin-bottom: 0.5rem;
    
}
</style>