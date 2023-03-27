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
      height: 100%;
      padding: 1rem;
      @include mixins.display-flex();

      img {
        object-fit: cover;
        height: 60%;
      }

      ul {
        height: 100%;
        width: 100%;
        @include mixins.display-flex($justify-content:space-around);
        list-style: none;
        font-size: 0.8rem;

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
          text-transform: uppercase;
          padding: 0.5rem 0;

          span {
            margin-left: 0.5rem;
          }
        }
      }
  }
}
</style>