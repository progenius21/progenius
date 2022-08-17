<template>
  <section id="home" class="w-full min-h-screen overflow-hidden px-5 lg:px-32 block xl:flex items-center justify-between text-dark relative" style="background-color:#03030b">
    <div class="prose prose-lg prose-invert relative z-10 my-32">
      <h1 class="" :class="{'animate__animated animate__fadeInDown animate__delay-03s animate__fast': !$route.hash}">Introducing Web3.0, Simply<span class="text-indigo-700 ">.</span></h1>
      <p :class="{'animate__animated animate__fadeInDown animate__delay-03s animate__fast': !$route.hash}">We are more than just investors. We are a group of highly-skilled, result-orientated individuals from various professional backgrounds all working towards educating and empowering our community.</p>
      <!-- Actions -->
      <div class="actions flex gap-5 mt-16" :class="{'animate__animated animate__fadeInDown animate__delay-1s animate__fast': !$route.hash}">
        <a href="http://community.progenius.io" class="px-5 md:px-10 py-3 flex gap-5 items-center justify-between rounded-full transition bg-indigo-700 hover:bg-indigo-500 text-white font-bold">
          <!-- prettier-ignore -->
          <span>Join our community</span>
        </a>
        <nuxt-link to="#about" class="p-3 flex gap-5 items-center justify-between rounded-full transition-all bg-transparent text-gray-200 hover:text-white font-bold no-underline	">Learn more</nuxt-link>
      </div>
      <!-- End Actions -->
    </div>
    <div class="w-full xl:w-1/2 absolute md:relative bottom-0 right-0">
      <img class="w-full" src="/an4.gif" loading="lazy" alt="">
    </div>
  </section>
</template>