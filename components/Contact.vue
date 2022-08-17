<template>
  <div>
    <contact-popup v-if="showPopup" @closed="showPopup = false" />
    <!-- prettier-ignore -->
    <section id="contact" class="w-full h-screen bg-black overflow-hidden py-16 px-5 lg:px-32 bg-gif xl:flex flex-col-reverse lg:flex-row justify-between items-end text-white relative">
    <div class="prose xl:prose-lg prose-invert relative z-10 h-2/3 relative mt-16 lg:mt-0">
      <h1 :class="{'animate__animated animate__fadeInDown animate__delay-03s': $route.hash === '#contact'}">Get in touch<span class="text-indigo-700">.</span></h1>
      <p :class="{'animate__animated animate__fadeInDown animate__delay-03s': $route.hash === '#contact'}">If you are as curious as we are, want to build something interesting that this space needs, and are looking for a partner who will strive to make it a success, get in touch. We'd love to collaborate.</p>
      <button :class="{'animate__animated animate__fadeInDown animate__delay-1s animate__fast': $route.hash === '#contact'}" @click="showPopup = true" class="block py-3 px-10 flex gap-5 mt-16 items-center justify-between rounded-full transition bg-indigo-700 hover:bg-indigo-500 text-white font-bold">Contact us</button>
      <div class="static lg:absolute bottom-0 mt-16" :class="{'animate__animated animate__fadeIn animate__delay-2s animate__fast': $route.hash === '#contact'}">
        <div class="flex gap-5 items-center">
          <!-- prettier-ignore -->
          <a class="transition opacity-75 hover:opacity-100" href="https://t.me/ProGeniuschat" target="_blank"><svg fill="white" width="24" role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>Telegram</title><path d="M11.944 0A12 12 0 0 0 0 12a12 12 0 0 0 12 12 12 12 0 0 0 12-12A12 12 0 0 0 12 0a12 12 0 0 0-.056 0zm4.962 7.224c.1-.002.321.023.465.14a.506.506 0 0 1 .171.325c.016.093.036.306.02.472-.18 1.898-.962 6.502-1.36 8.627-.168.9-.499 1.201-.82 1.23-.696.065-1.225-.46-1.9-.902-1.056-.693-1.653-1.124-2.678-1.8-1.185-.78-.417-1.21.258-1.91.177-.184 3.247-2.977 3.307-3.23.007-.032.014-.15-.056-.212s-.174-.041-.249-.024c-.106.024-1.793 1.14-5.061 3.345-.48.33-.913.49-1.302.48-.428-.008-1.252-.241-1.865-.44-.752-.245-1.349-.374-1.297-.789.027-.216.325-.437.893-.663 3.498-1.524 5.83-2.529 6.998-3.014 3.332-1.386 4.025-1.627 4.476-1.635z"/></svg></a>
          <!-- prettier-ignore -->
          <a class="transition opacity-75 hover:opacity-100" href="https://twitter.com/progeniusgroup" target="_blank"><svg fill="white" width="24" role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>Twitter</title><path d="M23.953 4.57a10 10 0 01-2.825.775 4.958 4.958 0 002.163-2.723c-.951.555-2.005.959-3.127 1.184a4.92 4.92 0 00-8.384 4.482C7.69 8.095 4.067 6.13 1.64 3.162a4.822 4.822 0 00-.666 2.475c0 1.71.87 3.213 2.188 4.096a4.904 4.904 0 01-2.228-.616v.06a4.923 4.923 0 003.946 4.827 4.996 4.996 0 01-2.212.085 4.936 4.936 0 004.604 3.417 9.867 9.867 0 01-6.102 2.105c-.39 0-.779-.023-1.17-.067a13.995 13.995 0 007.557 2.209c9.053 0 13.998-7.496 13.998-13.985 0-.21 0-.42-.015-.63A9.935 9.935 0 0024 4.59z"/></svg></a>
          <!-- prettier-ignore -->
          <a class="transition opacity-75 hover:opacity-100" href="https://www.instagram.com/progeniusgroup" target="_blank"><svg fill="white" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/></svg></a>
          <!-- prettier-ignore -->
          <a class="transition opacity-75 hover:opacity-100" href="#" target="_blank"><svg  fill="white" width="24" role="img" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><title>YouTube</title><path d="M23.498 6.186a3.016 3.016 0 0 0-2.122-2.136C19.505 3.545 12 3.545 12 3.545s-7.505 0-9.377.505A3.017 3.017 0 0 0 .502 6.186C0 8.07 0 12 0 12s0 3.93.502 5.814a3.016 3.016 0 0 0 2.122 2.136c1.871.505 9.376.505 9.376.505s7.505 0 9.377-.505a3.015 3.015 0 0 0 2.122-2.136C24 15.93 24 12 24 12s0-3.93-.502-5.814zM9.545 15.568V8.432L15.818 12l-6.273 3.568z"/></svg></a>
        </div>
        <p :class="{'animate__animated animate__fadeIn animate__delay-2s animate__fast': $route.hash === '#contact'}" class="text-sm">© 2022 ProfessionalGenius</p>
      </div>
    </div>
    <div class="w-full md:w-1/2 absolute bottom-0 right-0">
      <img class="w-full" src="/an.gif" loading="lazy" alt="">
    </div>
  </section>
  </div>
</template>
<script>
export default {
  data() {
    return {
      showPopup: false,
    }
  }
}
</script>
