<template lang="pug">
div#header
    nav.fixed-top.bg-light
        div#nav-container
            div#logo-box
                img#nav-logo(src="@/assets/images/logo_large.png")
            div#label-box
                span#logo-label Travel Agency
</template>

<script>
export default {
}
</script>

<style scoped>
@media(min-width: 0px) {
  #nav-container {
    flex-direction: column;
  }
}

@media(min-width: 481px) {
  #nav-container {
    flex-direction: row;
  }
}

#nav-container {
  display: flex;
  max-width: 1260px;
  margin: auto;
}

#logo-box {
  text-align: center;
}

#nav-logo {
  width: 6rem;
}

#label-box {
  text-align: center;
  margin: 20px;
}

#logo-label {
  font-family: "Pacifico";
  font-size: 2.2rem;
}
</style>
