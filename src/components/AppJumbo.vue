<template>
  <div id="jumbotron">
    
  </div>
</template>

<script>
export default {
  
}
</script>

<style lang="scss" scoped>
@use '../styles/partials/mixins';

  #jumbotron {
    @include mixins.background('../assets/img/jumbotron.jpg',top);
    height: 400px;
  }
</style>