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
        <a href="#"><img src="../assets/img/dc-logo.png" alt="dc logo"></a>
      </div>
      <ul>
        <li v-for="link in navLinks"><a :href="`#${link.text}`">{{link.text}}</a></li>
      </ul>
    </nav>
  </header>
</template>

<style scoped lang="scss">
  @use '../styles/partials/variables' as *;

  header {
    height: 120px;
    font-family: 'Open Sans Condensed', sans-serif;
    font-size: 1.2rem;

    li {
      position: relative;
      min-width: 3.5rem;

      a{color: $color-text-header;}
      
      &:hover {
        a {
          color: $color-primary;
        }
        &::after {
          content: '';
          height: 5px;
          position: absolute;
          bottom: -49px;
          left: 0;
          right: 0;
          background-color: $color-primary;
        }
      }
    }
  }

</style>