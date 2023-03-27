<script>
  import AppHeader from './components/AppHeader.vue';

  export default {
    components: {
      AppHeader,
    }
  }
</script>

<template>
  <AppHeader></AppHeader>
  
  <main>
    <div class="container">
      &rightarrow; Content goes here &leftarrow;
    </div>
    
  </main>
</template>

<style lang="scss">
  @import './styles/general.scss';
</style>
