<template>
  <!-- prettier-ignore -->
  <section id="faqs" class="w-full min-h-screen overflow-hidden px-5 lg:px-32 block flex flex-col-reverse xl:flex-row items-center justify-between text-dark relative" style="background-color:#fbfcf4">
    <div class="prose xl:prose-lg relative z-10 mt-32 w-full md:w-1/2">
      <h1 :class="{'animate__animated animate__fadeInDown animate__delay-03s animate__fast': $route.hash === '#faqs'}">Frequently asked questions<span class="text-indigo-700 ">.</span></h1>
      <div @click="currentQuestion = index" v-for="(faq, index) in faqs" :key="index" :class="{'animate__animated animate__fadeInDown animate__delay-1s animate__fast': $route.hash === '#faqs'}">
        <div class="cursor-pointer border border-gray-300 mb-5 p-5 text-left rounded-xl  w-full">
          <span class="font-medium">{{ faq.question }}</span>
          <div v-if="index === currentQuestion" class="font-normal text-base mt-5 text-gray-600 animate__animated animate__fadeInDown animate__faster">
            {{ faq.answer }}
          </div>
        </div>
      </div>
    </div>
    <div class="w-full" style="filter:invert(1)">
      <img class="w-2/3 xl:w-full max-w-2xl block m-auto relative top-10 xl:float-right" src="/an2.gif" loading="lazy" alt="">
    </div>
  </section>
</template>
<script>
export default {
  data() {
    return {
      currentQuestion: 0,
      faqs: [
        {
          question: 'What is progenius Private Network?',
          answer:
            'A private community of KOLs (Key Opinion Leaders), and Blockchain enthusiasts, contributing to development, stealth and public projects within the blockchain space',
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
            'You must complete the PG membership form to be considered. Due to the exclusivity of PG, you will be required to present what value you can add/offer to the group. You will be held accountable to the terms and conditions of the group.',
        },
      ],
    }
  }
}
</script>
