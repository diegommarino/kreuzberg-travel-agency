<template lang="pug">
div#place-card
    div.card(@mouseover="visible = 'visible'" @mouseleave="visible = 'hidden'")
        div.img-overlay
            img.card-img-top(:src="imgSrc")
            div.img-icon
                icon(name="search-plus" scale="4")
        div.card-body
            h2.card-title {{cardTitle}}
            p.card-text {{cardDescription}}
            div.prices-container(:style="{visibility: visible}")
                div.pill-container
                    div.pill-icon
                        icon(name="user" style="width: 40%")
                    div.pill-text 15€
                div.pill-container
                    div.pill-icon
                        icon(name="users")
                    div.pill-text 12€
                div.pill-container
                    div.pill-icon
                        icon(name="user-plus")
                    div.pill-text 10€
            button.btn.btn-lg.btn-block.card-btn(:style="{visibility: visible}")
                |Book Now
</template>

<script>
export default {
  props: ['imgSrc', 'cardTitle', 'cardDescription'],
  data () {
    return {
      visible: 'hidden'
    }
  }
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
  max-width: 100%;
  transition: all 0.3s;
}

.card:hover .card-img-top {
  filter: brightness(50%);
  transform: scale(1.4) rotate(-20deg);
}

.img-icon {
  color: white;
  transition: all .3s;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  text-align: center;
  opacity: 0;
}

.card:hover .img-icon {
  opacity: 1;
}

.img-overlay {
  overflow: hidden;
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

.prices-container {
  display: flex;
  justify-content: space-around;
}

.pill-container {
  flex-basis: 25%;
  display: flex;
  border: solid 1px;
  border-radius: 10%;
  border-color: #f0f0f0;
  background-color: #f0f0f0;
  margin: 10px;
}

.pill-icon {
  flex: 1;
  text-align: center;
}

.pill-text {
  flex: 1;
  text-align: center;
  font-size: 90%;
  background-color: white;
}

.card-btn {
  background-color: #D26258;
  font-family: 'Cuprum';
  border-radius: 0px;
}
</style>
