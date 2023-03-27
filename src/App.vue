<script>
  import AppHeader from './components/AppHeader.vue';
  import AppFooter from './components/AppFooter.vue';

  export default {
    components: {
      AppHeader,
      AppFooter,
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

  <AppFooter></AppFooter>
</template>

<style lang="scss">
  @import './styles/general.scss';
</style>
