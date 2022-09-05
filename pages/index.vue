<template>
  <div @wheel.prevent="scroll">
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
      class="hidden 2xl:block bullets"
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
video {
  pointer-events: none;
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
import { is } from '@babel/types';
import _ from 'lodash'
import { Promise } from 'q';
export default {
  data: function () {
    return {
      ts: 0,
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
      allowScroll: true,
    }
  },
  mounted: function () {
    let isChrome = /Chrome/.test(navigator.userAgent) && /Google Inc/.test(navigator.vendor);
    this.isNotMobile = window.innerWidth > 1280
    if(this.deviceType != 'desktop') {
      document.documentElement.style.overflow = 'unset'
    }
    addEventListener('keydown', (e) => {
      if(e.key == "ArrowUp") {
        this.scrollUp()
      }
      if(e.key == "ArrowDown") {
        this.scrollDown()
      }
    })
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
    scrollTo(index) {
      this.$router.replace({ hash: this.ids[this.ids.indexOf(this.$route.hash) - index] }).catch(err => {})
    },
    scrollUp() {
      this.scrollTo(1)
    },
    scrollDown() {
      this.scrollTo(-1)
    },
    test(e) {
      e.preventDefault()
      setTimeout(() => {
        if(this.allowScroll) {
          this.allowScroll = false
          if (e.deltaY < -0) {
            this.scrollUp()
            this.allowScroll = true
          } else if (e.deltaY > 0) {
            this.scrollDown()
            this.allowScroll = true
          }
        }
      }, 1000);
    },
    scroll(e) {
      if(e.timeStamp - this.ts >= 70) {
        if (e.deltaY < -0) {
          this.scrollUp()
        } else if (e.deltaY > 0) {
          this.scrollDown()
        }
      } else {
        this.ts = 0
      }
      // console.log(e.timeStamp - this.ts)
      this.ts = e.timeStamp - 15
    }
  },
}
</script>
