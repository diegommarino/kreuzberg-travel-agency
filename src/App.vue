<template lang="pug">
div#app
    app-header
    div#content-container
        app-place-section(:title="featured.title" :cards="featured.cards")
        app-place-section(:title="algarve.title" :cards="algarve.cards")
        app-place-section(:title="alentejo.title" :cards="alentejo.cards")
    app-footer
</template>

<script>
import Header from '@/components/navbars/Header.vue'
import Footer from '@/components/navbars/Footer.vue'
import PlaceSection from '@/components/place_cards/PlaceSection.vue'

export default {
  name: 'App',
  data () {
    return {
      featured: {
        title: 'Featured',
        cards: null
      },
      algarve: {
        title: 'Algarve',
        cards: null
      },
      alentejo: {
        title: 'Alentejo',
        cards: null
      },
      cards: [
        {
          imgSrc: 'albufeira_1024w.jpg',
          title: 'Albufeira',
          description: 'Usu an inani omnes. Eum te timeam dignissim disputando. Clita inimicus tincidunt no mei. Tollit officiis id per.'
        },
        {
          imgSrc: 'monte_gordo_1024w.jpg',
          title: 'Monte Gordo',
          description: 'Usu an inani omnes. Eum te timeam dignissim disputando. Clita inimicus tincidunt no mei. Tollit officiis id per.'
        },
        {
          imgSrc: 'odeceixe_1024w.jpg',
          title: 'Odeceixe',
          description: 'Usu an inani omnes. Eum te timeam dignissim disputando. Clita inimicus tincidunt no mei. Tollit officiis id per.'
        },
        {
          imgSrc: 'porto_covo_1024w.jpg',
          title: 'Porto Covo',
          description: 'Usu an inani omnes. Eum te timeam dignissim disputando. Clita inimicus tincidunt no mei. Tollit officiis id per.'
        },
        {
          imgSrc: 'sines_1024w.jpg',
          title: 'Sines',
          description: 'Usu an inani omnes. Eum te timeam dignissim disputando. Clita inimicus tincidunt no mei. Tollit officiis id per.'
        }
      ]
    }
  },
  components: {
    'app-header': Header,
    'app-footer': Footer,
    'app-place-section': PlaceSection
  },
  methods: {
    generateCards (qty) {
      let cards = []
      for (let i = 0; i < qty; i++) {
        const index = Math.floor(Math.random() * 5)
        cards.push(this.cards[index])
      }
      return cards
    }
  },
  mounted () {
    this.featured.cards = this.generateCards(5)
    this.algarve.cards = this.generateCards(10)
    this.alentejo.cards = this.generateCards(10)
  }
}
</script>

<style lang="scss">
@import "styles/main.scss";

@media(min-width:0px) {
  #app {
    margin-top: 220px;
  }
}

@media(min-width:481px) {
  #app {
    margin-top: 160px;
  }
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

#content-container {
  display: flex;
  flex-direction: column;
  max-width: 1260px;
  min-width: 320px;
  padding: 10px;
  margin: auto;
}
</style>
