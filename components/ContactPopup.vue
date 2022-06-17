<template>
  <!-- prettier-ignore -->
  <section class="fixed top-0 bottom-0 right-0 z-50 w-full lg:w-1/3 min-h-screen overflow-scroll m-auto py-15 p-5 lg:px-16 bg-white text-black">
    <div class="flex justify-between items-center ">
      <h1 v-if="!submitted" class="text-4xl font-bold">
        Contact us
      </h1>
      <div v-else></div>
      <button @click="$emit('closed')" class="cursor-pointer p-3 hover:bg-gray-100 border border-gray-500 rounded-full"><svg width="32" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" class="eva eva-close-outline" fill="inherit"><g data-name="Layer 2"><g data-name="close"><rect width="24" height="24" transform="rotate(180 12 12)" opacity="0"></rect><path d="M13.41 12l4.3-4.29a1 1 0 1 0-1.42-1.42L12 10.59l-4.29-4.3a1 1 0 0 0-1.42 1.42l4.3 4.29-4.3 4.29a1 1 0 0 0 0 1.42 1 1 0 0 0 1.42 0l4.29-4.3 4.29 4.3a1 1 0 0 0 1.42 0 1 1 0 0 0 0-1.42z"></path></g></g></svg></button>
    </div>
    <div class="m-auto h-full flex items-center" v-if="submitted">
      <div class="prose text-center w-full">
        <h1>THANK YOU FOR WRITING TO US.</h1>
        <p>
          We got your request and within 2 business days, we will get in touch.
        </p>
      </div>
    </div>
    <form v-else @submit.prevent="submit" class="mt-16">
      <div class="field mb-4">
        <label class="block text-gray-700 text-sm font-bold mb-2" for="fname">Full name</label>
        <input
          class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline focus:border-indigo-500"
          type="text"
          id="fname"
        />
      </div>
      <div class="field mb-4">
        <label class="block text-gray-700 text-sm font-bold mb-2" for="email">Email</label>
        <input
          class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline focus:border-indigo-500"
          type="email"
          id="email"
        />
      </div>
      <div class="field mb-4">
        <label class="block text-gray-700 text-sm font-bold mb-2" for="phone">Phone</label>
        <input
          class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline focus:border-indigo-500"
          type="phone"
          id="phone"
        />
      </div>
      <div class="field mb-4">
        <label class="block text-gray-700 text-sm font-bold mb-2" for="subject">Subject</label>
        <input
          class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline focus:border-indigo-500"
          type="text"
          id="subject"
        />
      </div>
      <div class="field mb-4">
        <label class="block text-gray-700 text-sm font-bold mb-2" for="message">Message</label>
        <textarea
          class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline focus:border-indigo-500"
          name="message"
          id="message"
          cols="30"
          rows="10"
        ></textarea>
      </div>
      <button
        type="submit"
        class="transition mt-10 py-5 px-10 font-bold rounded-full bg-indigo-700 text-white hover:bg-indigo-500"
      >
        Send message
      </button>
    </form>
  </section>
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
