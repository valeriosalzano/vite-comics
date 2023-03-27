<script>
import BlueBanner from '../components/BlueBanner.vue';
import FooterBanner from '../components/FooterBanner.vue';

export default {
  components: {
    BlueBanner,
    FooterBanner,
  },
  data() {
    return {
      navMenus: [
        [
          {
            title: 'DC COMICS',
          },{
            text: 'Characters',
            href: '#'
          },{
            text: 'Comics',
            href: '#'
          },{
            text: 'Movies',
            href: '#'
          },{
            text: 'TV',
            href: '#'
          },{
            text: 'Games',
            href: '#'
          },{
            text: 'Videos',
            href: '#'
          },{
            text: 'News',
            href: '#'
          },
        ],[
          {
            title: 'SHOP',
          },{
            text: 'Shop DC',
            href: '#'
          },{
            text: 'Shop DC Collectibles',
            href: '#'
          },
        ],[
          {
            title: 'DC',
          },{
            text: 'Terms Of Use',
            href: '#'
          },{
            text: 'Privacy policy (New)',
            href: '#'
          },{
            text: 'Ad Choices',
            href: '#'
          },{
            text: 'Advertising',
            href: '#'
          },{
            text: 'Jobs',
            href: '#'
          },{
            text: 'Subscriptions',
            href: '#'
          },{
            text: 'Talent Workshops',
            href: '#'
          },{
            text: 'CPSC Certificates',
            href: '#'
          },{
            text: 'Ratings',
            href: '#'
          },{
            text: 'Shop Help',
            href: '#'
          },{
            text: 'Contact Us',
            href: '#'
          },
        ],[
          {
            title: 'SITES',
          },{
            text: 'DC',
            href: '#'
          },{
            text: 'MAD Magazine',
            href: '#'
          },{
            text: 'DC Kids',
            href: '#'
          },{
            text: 'DC Universe',
            href: '#'
          },{
            text: 'DC Power Visa',
            href: '#'
          },
        ]
        
      ]
    }
  }
}
</script>

<template>
  <BlueBanner></BlueBanner>
  <div id="footer">
    <div class="container">
      <nav>
        <ul v-for="menu in navMenus">
          <li v-for="(link,index) in menu">
            <h3 v-if="index==0">{{link.title}}</h3>
            <a v-else :href="link.href">{{ link.text }}</a>
          </li>
        </ul>
      </nav>
      <img id="footer-bg-logo" src="../assets/img/dc-logo-bg.png">
    </div>
    <FooterBanner></FooterBanner>
  </div>
  
</template>

<style scoped lang="scss">
@use '../styles/partials/mixins';

  #footer {
    background-image: url("../assets/img/footer-bg.jpg");
    background-size: cover;

    .container {
      @include mixins.display-flex($justify-content:space-between);
      overflow: hidden;
      height: 360px;
    }
  }

  nav {
    @include mixins.display-flex(column,flex-start,flex-start);
    align-items: start;
    flex-wrap: wrap;
    height: 350px;
    padding: 1.5rem 0;

    * {
        text-align: start;
        color: white;
        width: 100%;
      }
    ul {
      height: unset;
      flex-direction: column;
      margin-bottom: 1rem;

      h3 {
        font-size: 1.2rem;
        margin-bottom: 0.5rem;
      }
      a {
        display: inline-block;
        text-transform: unset;
        font-size: 0.8rem;
        color: #797979;
        padding: 0;
        margin: 0.2rem 0;
      }
    }
  }
</style>