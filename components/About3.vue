<template>
  <!-- prettier-ignore -->
  <section id="about_c" class="w-full min-h-screen bg-white overflow-hidden py-32 px-5 lg:px-32 bg-gif flex flex-col lg:flex-row justify-between items-center text-black">
    <div class="prose xl:prose-lg z-10 my-32">
      <h1 :class="{'animate__animated animate__fadeInDown animate__delay-03s animate__fast': $route.hash === '#about_c'}">Are You Ready For The Digital Age?</h1>
      <p :class="{'animate__animated animate__fadeInDown animate__delay-03s animate__fast': $route.hash === '#about_c'}">Join our community to start networking and learning. Join our public telegram with the link below.</p>
      <a :class="{'animate__animated animate__fadeInDown animate__delay-1s animate__fast': $route.hash === '#about_c'}"  href="http://community.progenius.io" target="_blank"><button class="py-3 px-10 flex gap-5 mt-16 items-center justify-between rounded-full transition bg-indigo-700 hover:bg-indigo-500 text-white font-bold">Join our community</button></a>
    </div>
    <div class="w-full lg:w-1/3">
      <lottie :class="{'animate__animated animate__fadeIn animate__delay-2s animate__fast': $route.hash === '#about_c'}" :options="lottieOptions" v-on:animCreated="handleAnimation" />
    </div>
  </section>
</template>
<script>
import lottie from 'vue-lottie/src/lottie.vue'
import * as animationData from '~/static/animation_circle.json'

export default {
  components: {
    lottie,
  },
  data() {
    return {
      anim: null, // for saving the reference to the animation
      lottieOptions: { animationData: animationData.default },
    }
  },
  methods: {
    handleAnimation: function (anim) {
      this.anim = anim
    },
  },
}
</script>
