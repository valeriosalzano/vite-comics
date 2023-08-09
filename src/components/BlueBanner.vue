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
  background-color: variables.$color-primary;

  nav {
      img {
        height: 40%;
        margin-right: 0.5rem;
      }

      ul {
        flex-direction: column;
        flex-grow: 1;

        li {
          height: 200px;
          width: 100%;

          &:last-of-type img {
            height: 30%;
          }
        }
        a {
          width: 100%;
          color: white;
          height: 100%;
          @include mixins.display-flex();

          &:hover {
            backdrop-filter: brightness(70%);
          }
        }
      }
  }
}

@media screen and (min-width: 768px){
  #blue-banner{
    height: 150px;
    nav {

      ul {
      flex-direction: row;
      flex-wrap: nowrap;
      
        li {
          width: unset;
          height: 100%;
        }

      }
    }

  }
  
}

@media screen and (min-width: 1200px){
  #blue-banner{
    height: 150px;

    nav {

      ul {
      flex-direction: row;
      
        li {
          max-width: calc(20% - 0.5rem);
        }

      }
    }

  }
  
}
</style>