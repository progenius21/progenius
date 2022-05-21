<template>
  <div @keydown="handleScrollEvent" @mousewheel.prevent="handleScrollEvent">
    <div>
      <Navigation class="fixed top-0 z-99 left-0" />
      <Home />
      <About />
      <Pricing />
      <Faqs />
      <Contact />
    </div>
    <div
      class="bullets hidden"
      :class="{ light: ['#about', '#pricing'].indexOf($route.hash) > -1 }"
    >
      <NuxtLink to="/"></NuxtLink>
      <NuxtLink to="/#about"></NuxtLink>
      <NuxtLink to="#pricing"></NuxtLink>
      <NuxtLink to="#faqs"></NuxtLink>
      <NuxtLink to="#contact"></NuxtLink>
    </div>
  </div>
</template>
<style>
body {
  background-color: black;
  color: white;
}
html {
  scroll-behavior: smooth;
  overflow: hidden;
}

.bullets {
  position: fixed;
  right: 50px;
  top: 50%;
  z-index: 999;
}
.bullets a {
  display: block;
  width: 15px;
  height: 15px;
  margin-bottom: 10px;
  border-radius: 100px;
  border: 1px solid white;
}
.bullets.light a {
  border-color: black;
}
.bullets a.nuxt-link-exact-active {
  background: white;
}
.bullets.light a.nuxt-link-exact-active {
  background: black;
}
</style>
<script>
export default {
  data: function () {
    return {
      ids: ['', '#about', '#pricing', '#faqs', '#contact'],
      transition: false,
    }
  },
  methods: {
    resetTransition(delay) {
      setTimeout(() => {
        this.transition = false
      }, delay)
    },
    scrollTo(index) {
      this.$router.replace({ hash: this.ids[index] })
    },
    scrollUp() {
      this.transition = true
      this.scrollTo(this.ids.indexOf(this.$route.hash) - 1)
      this.resetTransition(300)
    },
    scrollDown() {
      this.transition = true
      this.scrollTo(this.ids.indexOf(this.$route.hash) + 1)
      this.resetTransition(300)
    },
    handleScrollEvent(e) {
      if (window.innerWidth > 600 && this.transition === false) {
        if (e.deltaY < -50 || e.keyCode === 38) {
          this.scrollUp()
        } else if (e.deltaY > 50 || e.keyCode === 40) {
          this.scrollDown()
        }
      }
    },
  },
}
</script>
