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
html {
  overflow: hidden;
  scroll-behavior: smooth;
}

body {
  background-color: black;
  color: white;
}
a {
  text-decoration: none!important;
}
.bullets {
  position: fixed;
  right: 80px;
  top: 50%;
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
.animate__delay-03s{
  animation-delay: .5s;
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
      preventscroll: false,
    }
  },
  mounted: function () {
    this.isNotMobile = window.innerWidth > 1280
    if(this.deviceType != 'desktop') {
      document.documentElement.style.overflow = 'unset'
    }
  },
  computed: {
    deviceType: function () {
      if (/(tablet|ipad|playbook|silk)|(android(?!.*mobi))/i.test(navigator.userAgent)) {
        return "tablet";
      }
      else if (/Mobile|Android|iP(hone|od)|IEMobile|BlackBerry|Kindle|Silk-Accelerated|(hpw|web)OS|Opera M(obi|ini)/.test(navigator.userAgent)) {
          return "mobile";
      }
      return "desktop";
    }
  },
  methods: {
    resetTransition(delay) {
      setTimeout(() => {
        this.preventscroll = false
      }, delay)
    },
    scrollTo(index) {
      this.$router.replace({ hash: this.ids[this.ids.indexOf(this.$route.hash) - index] })
    },
    scrollUp() {
      this.preventscroll = true
      this.scrollTo(1)
      this.resetTransition(300)
    },
    scrollDown() {
      this.preventscroll = true
      this.scrollTo(-1)
      this.resetTransition(300)
    },
    handleScrollEvent(e) {
      if (this.deviceType == 'desktop') {
        e.preventDefault()
      }
      if (this.deviceType == 'desktop' && this.preventscroll === false) {
        if (e.deltaY < -300 || e.keyCode === 38) {
          this.scrollUp()
        } else if (e.deltaY > 300 || e.keyCode === 40) {
          this.scrollDown()
        }
      }
    },
  },
}
</script>
