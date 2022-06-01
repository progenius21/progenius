<template>
  <div @keydown="handleScrollEvent" @mousewheel="handleScrollEvent">
    <div>
      <Navigation class="fixed top-0 left-0" />
      <Home />
      <About />
      <About2 />
      <About3 />
      <Pricing />
      <Faqs />
      <Contact />
    </div>
    <div
      class="bullets hidden lg:block"
      :class="{
        light: ['#about', '#faqs', '#about_c'].indexOf($route.hash) > -1,
      }"
    >
      <NuxtLink to="/"></NuxtLink>
      <NuxtLink to="/#about"></NuxtLink>
      <NuxtLink
        to="#about_b"
        :class="{
          'nuxt-link-exact-active ':
            ['#about_b'].indexOf(this.$route.hash) > -1,
        }"
      ></NuxtLink>
      <NuxtLink
        to="#about_c"
        :class="{
          'nuxt-link-exact-active ':
            ['#about_c'].indexOf(this.$route.hash) > -1,
        }"
      ></NuxtLink>
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

.bullets {
  position: fixed;
  right: 80px;
  top: 50%;
  z-index: 999;
  transition: border 0.4s;
}
.bullets a {
  display: block;
  width: 15px;
  height: 15px;
  margin-bottom: 10px;
  border-radius: 100px;
  border: 1px solid white;
  background: rgba(0, 0, 0, 0.3);
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
      isNotMobile: false,
      ids: [
        '',
        '#about',
        '#about_b',
        '#about_c',
        '#pricing',
        '#faqs',
        '#contact',
      ],
      transition: false,
    }
  },
  mounted: function () {
    this.isNotMobile = window.innerWidth > 600

    if (this.isNotMobile) {
      document.documentElement.style.scrollBehavior = 'smooth'
      document.documentElement.style.overflow = 'hidden'
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
      if (this.isNotMobile) {
        e.preventDefault()
      }
      if (this.isNotMobile && this.transition === false) {
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
