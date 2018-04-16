<template lang="pug">
div#place-section
    div.place-header
        hr.header-hr
        span.place-name {{title}}

    div.place-cards
        div.place-card(v-for="card in cards")
            app-place-card(:imgSrc="imgSrcPath(card.imgSrc)" :cardTitle="card.title" :cardDescription="card.description")
</template>

<script>
import PlaceCard from './PlaceCard.vue'
export default {
  props: ['title', 'cards'],
  components: {
    'app-place-card': PlaceCard
  },
  methods: {
    imgSrcPath (imgName) {
      const url = require(`@/assets/images/places/${imgName}`)
      return url
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

.header-hr {
  flex: 1;
  background-color: red;
  border-color: red;
}

.place-name {
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
