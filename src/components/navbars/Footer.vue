<template lang="pug">
div#footer
    div#container-content
        div#info
            div.container-info-item
                div.box-item-icon
                    icon(name="building")
                div.box-item-text
                    |Str. Mouzinho de Albuquerque
            div.container-info-item
                div.box-item-icon
                div.box-item-text
                    |8000-000 Faro
            div.container-info-item
                div.box-item-icon
                    icon(name="phone")
                div.box-item-text
                    |+351 289 123 45
            div.container-info-item
                div.box-item-icon
                    icon(name="envelope")
                div.box-item-text
                    |info@travelagency.com
        div#social-and-logo
            div#social-icons
                a(href="#" @click.prevent="")
                    icon(name="brands/facebook").social-icon
                a(href="#" @click.prevent="")
                    icon(name="brands/twitter").social-icon
                a(href="#" @click.prevent="")
                    icon(name="brands/pinterest").social-icon
                a(href="#" @click.prevent="")
                    icon(name="brands/instagram").social-icon
                a(href="#" @click.prevent="")
                    icon(name="brands/twitter-square").social-icon
            div#logo
                img#logo-img(src="@/assets/images/logo_large_bw.png")

</template>

<script>
export default {
}
</script>

<style scoped>
@media(min-width:0px){
  #container-content {
    flex-direction: column;
  }
}

@media(min-width:481px){
  #container-content {
    flex-direction: row;
  }
}

#footer {
  background-color: purple;
  padding: 1rem;
}

#container-content {
  display: flex;
  max-width: 1260px;
  margin: auto;
}

#info {
  flex: 1;
  display: flex;
  flex-direction: column;
  width: 300px;
  color: white;
}

.container-info-item {
  display: flex;
}

.box-item-icon {
  flex-basis: 10%;
}

.box-item-text {
  flex-basis: 90%;
  text-align: left;
}

#social-and-logo {
  flex: 2;
  display: flex;
  align-items: center;
}

#social-icons {
  flex: 2;
  width: 200px;
  text-align: center;
}

.social-icon {
  color: purple;
  background-color: white;
  margin: 0.3rem;
  width: 1.5rem;
  height: 1.5rem;
}

#logo {
  flex: 1;
  text-align: right;
}

#logo-img {
  width: 6rem;
}
</style>
