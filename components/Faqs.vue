<template>
  <div
    id="faqs"
    class="faqs w-full bg-white text-black flex items-center h-screen"
  >
    <div class="container m-auto flex items-center justify-between">
      <div class="hero w-1/2">
        <div class="content">
          <h1 class="text-6xl font-bold mb-10">FAQS</h1>
          <div v-for="(faq, index) in faqs" :key="index">
            <div
              class="cursor-pointer border font-bold border-gray-400 mb-5 p-5 text-left rounded-xl text-xl w-full"
            >
              {{ faq.question }}
              <div class="font-normal text-base mt-5 text-gray-600">
                {{ faq.answer }}
              </div>
            </div>
          </div>
        </div>
      </div>
      <img class="mt-16" src="/light-animation.gif" alt="" />
    </div>
  </div>
</template>
<script>
export default {
  data: function () {
    return {
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
}
</script>
