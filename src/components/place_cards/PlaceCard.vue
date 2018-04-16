<template lang="pug">
div#place-card
    div.card
        div.img-overlay
            img.card-img-top(:src="imgSrc")
        div.card-body
            h2.card-title {{cardTitle}}
            p.card-text {{cardDescription}}

</template>

<script>
export default {
  props: ['imgSrc', 'cardTitle', 'cardDescription']
}
</script>

<style scoped>
.card-title {
  text-align: center;
  margin-top: 10px;
  font-family: "Pacifico";
  color: purple;
}

.card, .card-img-top {
  margin: auto;
}

.card-img-top {
  width: 100%;
}
.img-overlay {
  position: relative;
  text-align: center;
}
.img-overlay::after {
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  bottom: 0;
  border: 15px transparent solid;
  border-bottom: 15px white solid;
  content: '';
}

.card-text {
  text-align: justify;
}
</style>
