<script>
  import AppHeader from './components/AppHeader.vue';
  import AppFooter from './components/AppFooter.vue';
  import AppJumbo from "./components/AppJumbo.vue";
  import AppSectionCurrentSeries from "./components/AppSectionCurrentSeries.vue";

  import ComicsData from "./assets/data/dc-comics.json";

  import "@fontsource/open-sans-condensed";
  import "@fontsource/open-sans";

  export default {
    components: {
      AppHeader,
      AppFooter,
      AppJumbo,
      AppSectionCurrentSeries,
    },
    ComicsData,
  }
</script>

<template>
  <body>
    <AppHeader></AppHeader>
    <main>
      <AppJumbo></AppJumbo>
      <AppSectionCurrentSeries :comics = "$options.ComicsData"/>
    </main>

    <AppFooter></AppFooter>
  </body>
  
</template>

<style lang="scss">
  @import './styles/general.scss';
  
</style>
