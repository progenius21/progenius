<template>
  <div
    class="fixed lg:absolute bottom-0 right-0 z-50 w-full lg:w-1/3 h-screen m-auto py-16 p-5 lg:px-16 bg-white text-black"
  >
    <div class="flex justify-between items-center mb-16">
      <h1 v-if="!submitted" class="text-4xl lg:text-6xl font-bold">
        Get in touch.
      </h1>
      <div v-else></div>
      <span @click="$emit('closed')" class="cursor-pointer text-xl font-bold"
        >X Close
      </span>
    </div>
    <div class="m-auto h-full flex items-center" v-if="submitted">
      <div class="w-full text-center">
        <h1 class="text-4xl font-bold">THANK YOU FOR WRITING TO US.</h1>
        <p>
          We got your request and within 2 business days, we will get in touch.
        </p>
      </div>
    </div>
    <form v-else @submit.prevent="submit">
      <div class="field">
        <label class="block mb-3" for="fname">Full name</label>
        <input
          class="w-full block mb-5 border border-gray-400 p-3 rounded"
          type="text"
          id="fname"
        />
      </div>
      <div class="field">
        <label class="block mb-3" for="email">Email</label>
        <input
          class="w-full block mb-5 border border-gray-400 p-3 rounded"
          type="email"
          id="email"
        />
      </div>
      <div class="field">
        <label class="block mb-3" for="phone">Phone</label>
        <input
          class="w-full block mb-5 border border-gray-400 p-3 rounded"
          type="phone"
          id="phone"
        />
      </div>
      <div class="field">
        <label class="block mb-3" for="subject">Subject</label>
        <input
          class="w-full block mb-5 border border-gray-400 p-3 rounded"
          type="text"
          id="subject"
        />
      </div>
      <div class="field">
        <label class="block mb-3" for="message">Message</label>
        <textarea
          class="w-full block mb-5 border border-gray-400 p-3 rounded"
          name="message"
          id="message"
          cols="30"
          rows="10"
        ></textarea>
      </div>
      <button
        type="submit"
        class="transition mt-10 py-5 px-10 font-bold rounded bg-indigo-700 text-white hover:bg-indigo-500"
      >
        Send message
      </button>
    </form>
  </div>
</template>
<script>
export default {
  data: function () {
    return {
      submitted: false,
    }
  },
  methods: {
    submit: function () {
      this.submitted = true
    },
  },
}
</script>
