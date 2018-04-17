<template lang="pug">
div#header
    nav.fixed-top.bg-light
        div.nav-container
            div.logo-box
                img.nav-logo(src="@/assets/images/logo_large.png")
            div.label-box
                span.logo-label Travel Agency
</template>

<script>
export default {
  data () {
    return {
      scrolled: false
    }
  },
  methods: {
    handleScroll () {
      if (window.scrollY > 150) {
        document.getElementsByClassName('nav-logo')[0].classList.add('shrink-logo')
        document.getElementsByClassName('logo-label')[0].classList.add('shrink-label')
      } else {
        document.getElementsByClassName('nav-logo')[0].classList.remove('shrink-logo')
        document.getElementsByClassName('logo-label')[0].classList.remove('shrink-label')
      }
      console.log('teste')
    }
  },
  beforeMount () {
    window.addEventListener('scroll', this.handleScroll)
  },
  beforeDestroy () {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style scoped>
@media(min-width: 0px) {
  .nav-container {
    flex-direction: column;
  }
}

@media(min-width: 481px) {
  .nav-container {
    flex-direction: row;
  }
}

.nav-container {
  display: flex;
  max-width: 1260px;
  margin: auto;
}

.logo-box {
  text-align: center;
}

.nav-logo {
  width: 6rem;
  transition: all 0.3s;
}

.label-box {
  text-align: center;
  margin: 20px;
}

.logo-label {
  font-family: "Pacifico";
  font-size: 2.2rem;
  transition: all 0.3s;
}

.shrink-logo {
  width: 4rem;
}

.shrink-label {
  font-size: 1.2rem;
}
</style>
