<template>
  <div id="AppSectionCurrentSeries">
    <ul class="container">
      <div class="label">current series</div>
      <li v-for="(comic, index) in comics" :key="index">
        <div class="img-container"><img :src="getImagePath(comic.thumb)" :alt="comic.series"></div>
        <h3>{{ comic.series }}</h3>
      </li>
    </ul>
    <div class="btns-container">
      <button type="button" class="btn">load more</button>
    </div>
    
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: 'AppSectionCurrentSeries',
    }
  },
  props: {
    comics: Array,
  },
  methods: {
    getImagePath (img) {
      return new URL(img , import.meta.url).href;
    }
  },
}
</script>

<style lang="scss" scoped>
@use '../styles/partials/mixins';
@use '../styles/partials/variables' as *;


ul {
  position: relative;
  @include mixins.display-flex($align:flex-start);
  list-style: none;
  padding: 3rem 1rem;

  .label {
    position: absolute;
    top: 0;
    left: 1rem;
    transform: translateY(-50%);
    padding: 0.5rem 1rem;
    background-color: $color-primary;
    text-transform: uppercase;
    font-family: 'Open Sans Condensed',sans-serif;
    font-weight: bold;
  }

  li {
    width: calc(100% / 6 - 1rem);
    margin: 1rem 0.5rem;

    .img-container {
      overflow: hidden;
    }

    img {
      height: 300px;
    }

    h3 {
      font-size: 1rem;
      font-weight: 300;
      text-transform: uppercase;
      font-family: 'Open Sans', sans-serif;
      text-align: center;
    }
  }
}

button {
  border: none;
  background-color: $color-primary;
  padding: 0.5rem 3rem;
  text-transform: uppercase;
  text-align: center;
  color: white;
  font-weight: bold;
}
  
</style>