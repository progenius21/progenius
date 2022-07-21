<template>
  <!-- prettier-ignore -->
  <section id="about" class="w-full min-h-screen bg-white overflow-hidden py-32 px-5 lg:px-32 bg-gif flex flex-col lg:flex-row justify-between items-center text-black">
    <div class="prose lg:prose-xl z-10 my-32">
      <h1 :class="{'animate__animated animate__fadeInDown animate__delay-03s animate__fast': $route.hash === '#about'}">The world is digitising. <br />Web 3.0 is inevitable<span class="text-indigo-700 ">.</span></h1>
      <p :class="{'animate__animated animate__fadeInDown animate__delay-03s animate__fast': $route.hash === '#about'}">Professional Genius aims to educate anyone and everyone, whatever their level of experience, about cryptocurrency and its importance. ProGenius also strives to provide top quality information for avid investors regarding high quality cryptocurrency projects at the earliest stages of their development.</p>
      <a href="http://community.progenius.io" :class="{'animate__animated animate__fadeInDown animate__delay-1s animate__fast': $route.hash === '#about'}" to="/#contact"><button class="py-3 px-10 flex gap-5 mt-16 items-center justify-between rounded-full transition bg-indigo-700 hover:bg-indigo-500 text-white font-bold">Join community</button></a>
    </div>
    <div class="w-full lg:w-1/3">
      <lottie :class="{'animate__animated animate__fadeIn animate__delay-2s animate__fast': $route.hash === '#about'}" :options="lottieOptions" v-on:animCreated="handleAnimation" />
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
