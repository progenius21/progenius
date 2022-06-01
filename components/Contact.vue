<template>
  <div>
    <contact-popup v-if="showPopup" @closed="showPopup = false" />

    <div
      id="contact"
      class="bg-black text-white flex items-center py-32 px-5 h-screen lg:px-32"
    >
      <div class="relative flex items-center justify-between w-full gap-10">
        <div class="lg-w-1/2">
          <div class="content">
            <h1 class="text-6xl font-bold">Get in touch.</h1>
            <p class="mt-10 text-lg text-gray-300">
              If you are as curious as we are, building something interesting
              that the space needs, and looking for a partner who will strive to
              make it a success, get in touch. We'd love to collaborate.
            </p>
            <div class="actions flex gap-5">
              <button
                @click="showPopup = true"
                class="transition mt-10 py-5 px-10 font-bold rounded-full bg-indigo-700 text-white hover:bg-indigo-500"
              >
                Contact us
              </button>
            </div>
          </div>
          <div class="mt-32 flex gap-5 items-center">
            <!-- prettier-ignore -->
            <a class="transition opacity-75 hover:opacity-100" href="#" target="_blank"><svg fill="white" width="24" role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>Telegram</title><path d="M11.944 0A12 12 0 0 0 0 12a12 12 0 0 0 12 12 12 12 0 0 0 12-12A12 12 0 0 0 12 0a12 12 0 0 0-.056 0zm4.962 7.224c.1-.002.321.023.465.14a.506.506 0 0 1 .171.325c.016.093.036.306.02.472-.18 1.898-.962 6.502-1.36 8.627-.168.9-.499 1.201-.82 1.23-.696.065-1.225-.46-1.9-.902-1.056-.693-1.653-1.124-2.678-1.8-1.185-.78-.417-1.21.258-1.91.177-.184 3.247-2.977 3.307-3.23.007-.032.014-.15-.056-.212s-.174-.041-.249-.024c-.106.024-1.793 1.14-5.061 3.345-.48.33-.913.49-1.302.48-.428-.008-1.252-.241-1.865-.44-.752-.245-1.349-.374-1.297-.789.027-.216.325-.437.893-.663 3.498-1.524 5.83-2.529 6.998-3.014 3.332-1.386 4.025-1.627 4.476-1.635z"/></svg></a>
            <!-- prettier-ignore -->
            <a class="transition opacity-75 hover:opacity-100" href="#" target="_blank"><svg  fill="white" width="24" role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>YouTube</title><path d="M23.498 6.186a3.016 3.016 0 0 0-2.122-2.136C19.505 3.545 12 3.545 12 3.545s-7.505 0-9.377.505A3.017 3.017 0 0 0 .502 6.186C0 8.07 0 12 0 12s0 3.93.502 5.814a3.016 3.016 0 0 0 2.122 2.136c1.871.505 9.376.505 9.376.505s7.505 0 9.377-.505a3.015 3.015 0 0 0 2.122-2.136C24 15.93 24 12 24 12s0-3.93-.502-5.814zM9.545 15.568V8.432L15.818 12l-6.273 3.568z"/></svg></a>
            <!-- prettier-ignore -->
            <a class="transition opacity-75 hover:opacity-100" href="#" target="_blank"><svg fill="white" width="24" role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>Facebook</title><path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"/></svg></a>
            <!-- prettier-ignore -->
            <a class="transition opacity-75 hover:opacity-100" href="#" target="_blank"><svg fill="white" width="24" role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>Twitter</title><path d="M23.953 4.57a10 10 0 01-2.825.775 4.958 4.958 0 002.163-2.723c-.951.555-2.005.959-3.127 1.184a4.92 4.92 0 00-8.384 4.482C7.69 8.095 4.067 6.13 1.64 3.162a4.822 4.822 0 00-.666 2.475c0 1.71.87 3.213 2.188 4.096a4.904 4.904 0 01-2.228-.616v.06a4.923 4.923 0 003.946 4.827 4.996 4.996 0 01-2.212.085 4.936 4.936 0 004.604 3.417 9.867 9.867 0 01-6.102 2.105c-.39 0-.779-.023-1.17-.067a13.995 13.995 0 007.557 2.209c9.053 0 13.998-7.496 13.998-13.985 0-.21 0-.42-.015-.63A9.935 9.935 0 0024 4.59z"/></svg></a>
          </div>
          <p class="mt-32">© 2022 ProfessionalGenius | Privacy Policy</p>
        </div>
        <img class="hidden lg:block" src="/dark-animation.gif" alt="" />
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data: function () {
    return { showPopup: false }
  },
}
</script>
