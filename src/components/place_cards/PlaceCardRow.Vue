<template lang="pug">
div#place-card
    div.card
        div.img-overlay
            img.card-img-top(:src="imgSrc")
            div.img-icon
                icon(name="search-plus" scale="4")
        div.card-body
            h2.card-title {{cardTitle}}
            p.card-text {{cardDescription}}
            div.prices-container
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
        button.btn.btn-lg.btn-block.card-btn
            |Book Now
</template>

<script>
export default {
  props: ['imgSrc', 'cardTitle', 'cardDescription']
}
</script>

<style scoped>
.card {
  border: solid;
  border-width: 0px;
  border-color: #f0f0f0;
  border-radius: 5px;
  transition: all .3s;
  display: flex;
  flex-direction: row;
}

.card .img-overlay {
  flex-basis: 250px;
  align-self: center;
}

.card, .card-img-top {
  margin: auto;
}

.img-overlay .card-img-top {
  max-width: 100%;
  transition: all .3s;
}

.card .card-body {
  flex: 1;
  padding: 15px;
}

.card-title {
  margin-top: 10px;
  font-family: "Pacifico";
  color: purple;
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

.img-overlay {
  overflow: hidden;
  position: relative;
  text-align: center;
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
  flex: 1;
  align-self: center;
  transition: all .3s;
  height: 50px;
}

.img-overlay::after {
  position: absolute;
  right: 0;
  transform: translateY(50%);
  bottom: 50%;
  border: 15px transparent solid;
  border-right: 15px white solid;
  content: '';
}

.card:hover .card-img-top {
  filter: brightness(50%);
  transform: scale(1.4) rotate(-20deg);
}

.card:hover .img-icon {
  opacity: 1;
}

.card:hover .card-btn {
  height: 200px;
}

.card:hover {
  border-width: 1px;
}

</style>
