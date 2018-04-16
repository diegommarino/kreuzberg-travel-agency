<template lang="pug">
div#place-section
    div.place-header(@mouseover="showDisplayButton = true" @mouseleave="showDisplayButton = false")
        div(v-if="shouldDisplayButton")
            button.btn.display-button(v-if="displayList" @click="displayList = false")
                icon(name="th-large")
            button.btn.display-button(v-if="!displayList" @click="displayList = true")
                icon(name="list-ul")
        hr
        span.name {{title}}

    div.place-cards(:style="{'flex-direction': flexDirection}")
        div.place-card(v-if="!displayList" v-for="card in cards")
            app-place-card(:imgSrc="imgSrcPath(card.imgSrc)" :cardTitle="card.title" :cardDescription="card.description")
        div.place-card(v-if="displayList" v-for="card in cards")
            app-place-card-row(:imgSrc="imgSrcPath(card.imgSrc)" :cardTitle="card.title" :cardDescription="card.description")
</template>

<script>
import PlaceCard from './PlaceCard.vue'
import PlaceCardRow from './PlaceCardRow.vue'
export default {
  props: ['title', 'cards'],
  components: {
    'app-place-card': PlaceCard,
    'app-place-card-row': PlaceCardRow
  },
  data () {
    return {
      displayList: false,
      showDisplayButton: false
    }
  },
  methods: {
    imgSrcPath (imgName) {
      const url = require(`@/assets/images/places/${imgName}`)
      return url
    }
  },
  computed: {
    shouldDisplayButton () {
      const isFeatured = (this.title !== 'Featured')
      const isHeaderHobered = this.showDisplayButton
      const isScreenSize768 = window.screen.width >= 1024
      return isFeatured && isHeaderHobered && isScreenSize768
    },
    flexDirection () {
      return (this.displayList ? 'column' : 'row')
    }
  }
}
</script>

<style scoped>
@media(min-width: 0px) {
  .place-card {
    flex-basis: 100%;
  }
}

@media(min-width: 480px) {
  .place-card {
    flex-basis: 45%;
    margin: 2.5%;
  }
}

@media(min-width: 768px) {
  .place-card {
    flex-basis: 30%;
    margin: 1.6%;
  }
}

@media(min-width: 1024px) {
  .place-card {
    flex-basis: 22%;
    margin: 1.5%;
  }
}

@media(min-width: 1260px) {
  .place-card {
    flex-basis: 18%;
    margin: 1%;
  }
}

#place-section {
  display: flex;
  flex-direction: column;
}

.place-header {
  flex: 1;
  margin-bottom: 20px;
  display: flex;
  color: red;
  align-items: center;
}

.place-header .display-button {
  margin: 10px;
  background-color: #f0f0f0;
}

.place-header hr {
  flex: 1;
  background-color: red;
  border-color: red;
}

.place-header .name {
  text-align: right;
  font-family: "Pacifico";
  font-size: 2rem;
}

.place-cards {
  flex: 1;
  display: flex;
  flex-wrap: wrap;
}
</style>
