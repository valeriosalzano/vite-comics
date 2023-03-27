<script>
export default {
  data() {
    return {
      name: 'AppHeader',
      navLinks: [
        {
          text: 'characters',
        },{
          text: 'comics',
        },{
          text: 'movies',
        },{
          text: 'tv',
        },{
          text: 'games',
        },{
          text: 'collectibles',
        },{
          text: 'videos',
        },{
          text: 'fans',
        },{
          text: 'news',
        },{
          text: 'shop',
        },

      ]
    }
  },
}
</script>

<template>
  <header>
    <nav class="container">
      <div class="img-container">
        <a href="#"><img src="../assets/img/dc-logo.png" alt=""></a>
      </div>
      <ul>
        <li v-for="link in navLinks"><a :href="`#${link.text}`">{{link.text}}</a></li>
      </ul>
    </nav>
  </header>
</template>

<style scoped lang="scss">
  @use '../styles/partials/variables';

  header {
    height: 120px;

    nav {
      padding: 1rem 0.5rem;
      li {
        position: relative;

        &:hover {
          &::after {
            content: '';
            height: 5px;
            position: absolute;
            bottom: -52px;
            left: 0.5rem;
            right: 0.5rem;
            background-color: variables.$color-primary;
          }
          a {
            color: variables.$color-primary;
          }
        }
      }
    }
  }

</style>