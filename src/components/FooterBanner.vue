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
          <span>follow us</span>
          <ul>
            <li v-for="icon in navIcons"><a href="#"><img :src="getImagePath(icon.image)" :alt="icon.social"></a></li>
          </ul>
        </div>
      </nav>
    </div>
  </div>
  
</template>

<style scoped lang="scss">
@use '../styles/partials/mixins';
@use '../styles/partials/variables';

#footer-banner {
  background-color: #303030;
}
  nav {
    .call-to-action {
      text-transform: uppercase;
      color: white;
      padding: 1rem 1.5rem;
      border: 3px solid variables.$color-primary;
    }
    .social-container {
      @include mixins.display-flex();

      span {
        text-transform: uppercase;
        color: variables.$color-primary;
        font-weight: bold;
        font-size: 1.2rem;
      }

      li {
        filter: hue-rotate(90deg);
      }
    }
  }
</style>