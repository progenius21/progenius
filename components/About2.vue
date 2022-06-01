<template>
  <!-- prettier-ignore -->
  <section id="about_b" class="w-full min-h-screen bg-black overflow-hidden py-32 px-5 lg:px-32 bg-gif flex flex-col lg:flex-row justify-between items-center text-white">
    <div class="prose lg:prose-xl prose-invert z-10 mt-32">
      <h1>Our Focus<span class="text-indigo-700 ">.</span></h1>
      <p>Here at Professional Genius (PG), We are more than just investors. We are a group of highly-skilled, result-orientated individuals from various professional backgrounds all working towards educating and empowering our community.</p>
      <button class="block py-3 px-10 flex gap-5 items-center justify-between rounded-full transition bg-indigo-700 hover:bg-indigo-500 text-white font-bold">Join our community</button>
    </div>
    <lottie class="w-1/2" :options="lottieOptions" v-on:animCreated="handleAnimation" />
  </section>
</template>
<script>
import lottie from 'vue-lottie/src/lottie.vue'
import * as animationData from '~/static/animation.json'

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
