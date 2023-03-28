<script>
export default {
  data(){
    return {
      name: 'FooterBanner',
      navIcons: [
        {
          social: 'facebook',
          image: 'footer-facebook.png',
        },{
          social: 'twitter',
          image: 'footer-twitter.png',
        },{
          social: 'youtube',
          image: 'footer-youtube.png',
        },{
          social: 'pinterest',
          image: 'footer-pinterest.png',
        },{
          social: 'periscope',
          image: 'footer-periscope.png',
        },
      ]
    }
  },
  methods: {
    getImagePath (img) {
      return new URL(`../assets/img/${img}`, import.meta.url).href;
    }
  }
}
</script>

<template>
  <div id="footer-banner">
    <div class="container">
      <nav>
        <a class="call-to-action" href="#">sign-up now!</a>
        <div class="social-container">
          <p>follow us</p>
          <ul>
            <li v-for="icon in navIcons"><a href="#"><img :src="getImagePath(icon.image)" :alt="`${icon.social} logo`"></a></li>
          </ul>
        </div>
      </nav>
    </div>
  </div>
  
</template>

<style scoped lang="scss">
@use '../styles/partials/mixins';
@use '../styles/partials/variables' as *;

#footer-banner {
  background-color: $color-bg-footer-banner;
}
  nav {
    .call-to-action {
      text-transform: uppercase;
      color: $color-text-btn;
      padding: 1rem 1.5rem;
      border: 3px solid $color-primary;
      &:hover {
        background-color: $color-primary;
      }
    }
    .social-container {
      @include mixins.display-flex();

      p {
        font-family: 'Open Sans Condensed', sans-serif;
        text-transform: uppercase;
        color: $color-primary;
        font-size: 1.5rem;
        margin-right: 1rem;
      }
    }
  }
</style>