<template>
  <div id="app">
    <MainWrapper />
    <router-view/>
  </div>
</template>

<script>
  import MainWrapper from '@/components/MainWrapper.vue'
  
  export default {
    name: 'App',
    components: {
      MainWrapper,
    }
  }
</script>  

<style lang="scss">

</style>
