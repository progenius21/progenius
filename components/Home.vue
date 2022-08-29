<template>
  <section id="home" class="w-full min-h-screen overflow-hidden px-5 lg:px-32 block flex flex-col-reverse xl:flex-row items-center  text-dark relative" style="background-color:#03040b">
    <div class="prose prose-sm lg:prose-md 3xl:prose-xl prose-invert relative z-10 mb-32 mt-10 xl:my-32">
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
    <div class="w-full
    ">
      <video controls="false" playsinline autoplay muted loop class="w-full max-w-3xl block m-auto top-10 xl:top-0 relative xl:float-right" loading="lazy">
        <source src="/an3.mp4" type="video/mp4">
      </video>
    </div>
  </section>
</template>