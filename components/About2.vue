<template>
  <!-- prettier-ignore -->
  <section id="about_b" class="w-full min-h-screen overflow-hidden px-5 lg:px-32 block flex flex-col-reverse xl:flex-row items-center justify-between text-dark relative" style="background-color:#03030b">
    <div class="prose xl:prose-lg prose-invert relative z-10 my-32">
      <h1 :class="{'animate__animated animate__fadeInDown animate__delay-03s animate__fast': $route.hash === '#about_b'}">Our Focus<span class="text-indigo-700 ">.</span></h1>
      <p :class="{'animate__animated animate__fadeInDown animate__delay-03s animate__fast': $route.hash === '#about_b'}">We are more than just investors. We are a group of highly-skilled, result-orientated individuals from various professional backgrounds, all working towards educating and empowering our community.</p>
      <a :class="{'animate__animated animate__fadeInDown animate__delay-1s animate__fast': $route.hash === '#about_b'}"  href="http://community.progenius.io" target="_blank"><button class="py-3 px-10 flex gap-5 mt-16 items-center justify-between rounded-full transition bg-indigo-700 hover:bg-indigo-500 text-white font-bold">Join our community</button></a>
    </div>
    <div class="w-full">
      <img class="w-2/3 xl:w-full max-w-2xl block m-auto relative top-10" src="/an2.gif" loading="lazy">
    </div>
  </section>
</template>
