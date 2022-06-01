<template>
  <!-- prettier-ignore -->
  <section id="faqs" class="w-full min-h-screen bg-white overflow-hidden py-32 px-5 lg:px-32 bg-gif flex flex-col lg:flex-row justify-between items-center text-black">
    <div class="prose lg:prose-xl z-10 mt-32">
      <h1>Frequently asked questions<span class="text-indigo-700 ">.</span></h1>
      <div v-for="(faq, index) in faqs" :key="index">
        <div class="cursor-pointer border border-gray-300 mb-5 p-5 text-left rounded-xl text-xl w-full">
          <span class="font-medium">{{ faq.question }}</span>
          <div class="font-normal text-base mt-5 text-gray-600">
            {{ faq.answer }}
          </div>
        </div>
      </div>
    </div>
    <lottie class="hidden lg:block w-1/2" :options="lottieOptions" v-on:animCreated="handleAnimation" />
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
      faqs: [
        {
          question: 'What is progenius Private Network?',
          answer:
            'A private community of KOLs (Key Opinion Leaders), and Blockchain enthusiasts contributing to development, stealth and public projects within the blockchain space.',
        },
        {
          question: 'What is the Pro Genius referral program?',
          answer:
            'PG operates on a referral basis where you can only join the group via an existing member.',
        },
        {
          question: 'Can I join the private network at any time?',
          answer: 'PG will notify your referee when a space becomes available.',
        },
        {
          question: 'What conditions must be met for me to join the group?',
          answer:
            'You must complete the PG membership form to be considered. Due to the exclusivity of PG, you will be required to present what value you can add/offer to the group. You will be held accountable for the terms and conditions of the group.',
        },
      ],
    }
  },
  methods: {
    handleAnimation: function (anim) {
      this.anim = anim
    },
  },
}
</script>
