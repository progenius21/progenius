<template>
  <!-- prettier-ignore -->
  <section id="about_c" class="w-full min-h-screen bg-white overflow-hidden py-32 px-5 lg:px-32 bg-gif flex flex-col lg:flex-row justify-between items-center text-black">
    <div class="prose lg:prose-xl z-10 mt-32">
      <h1>Are You Ready For The Digital Age?</h1>
      <p>Join our community to start networking and learning. Join our public telegram with the link below.</p>
      <a to="#" target="_blank"><button class="py-3 px-10 flex gap-5 items-center justify-between rounded-full transition bg-indigo-700 hover:bg-indigo-500 text-white font-bold">Join our community</button></a>
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
