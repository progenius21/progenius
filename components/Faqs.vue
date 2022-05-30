<template>
  <div
    id="faqs"
    class="bg-white text-black flex items-center py-32 px-5 h-screen lg:pt-20 lg:px-32"
  >
    <div class="flex items-center justify-between z-10 relative">
      <div class="lg:w-1/2">
        <div class="content">
          <h1 class="text-5xl font-bold mb-10">Frequently asked questions</h1>
          <div v-for="(faq, index) in faqs" :key="index">
            <div
              class="cursor-pointer border border-gray-300 mb-5 p-5 text-left rounded-xl text-xl w-full"
            >
              <span class="font-medium">{{ faq.question }}</span>
              <div class="font-normal text-base mt-5 text-gray-600">
                {{ faq.answer }}
              </div>
            </div>
          </div>
        </div>
      </div>
      <img class="hidden lg:block" src="/light-animation.gif" alt="" />
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
