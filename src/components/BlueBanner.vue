<script>
export default {
  data() {
    return {
      name: 'BlueBanner',
      navLinks: [
        {
          text: 'digital comics',
          image: 'buy-comics-digital-comics.png',
        },{
          text: 'dc merchandise ',
          image: 'buy-comics-merchandise.png',
        },{
          text: 'subscription ',
          image: 'buy-comics-subscriptions.png',
        },{
          text: 'comic shop locator ',
          image: 'buy-comics-shop-locator.png',
        },{
          text: 'dc power visa',
          image: 'buy-dc-power-visa.svg',
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
  <div id="blue-banner">
    <nav class="container">
      <ul>
        <li v-for="link in navLinks">
          <a href="#">
            <img :src="getImagePath(link.image)" :alt="link.text">
            <span>
              {{ link.text }}
            </span>
          </a>
        </li>
      </ul>

    </nav>
  </div>
  
</template>

<style scoped lang="scss">
@use '../styles/partials/variables';
@use '../styles/partials/mixins';

#blue-banner {
  height: 150px;
  background-color: variables.$color-primary;

  nav {
      img {
        object-fit: cover;
        height: 60%;
      }

      ul {
        width: 100%;

        li {
          width: calc(20% - 1rem);
          height: 100%;

          &:last-of-type img {
            height: 40%;
          }
        }
        a {
          color: white;
          height: 100%;
          @include mixins.display-flex();

          span {
            margin-left: 0.5rem;
          }
        }
      }
  }
}
</style>