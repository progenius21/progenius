<template>
  <!-- prettier-ignore -->
  <section id="about_c" class="w-full min-h-screen overflow-hidden px-5 lg:px-32 block flex flex-col-reverse xl:flex-row items-center justify-between text-dark relative" style="background-color:#fbfcf4">
    <div class="prose xl:prose-md relative z-10 mb-32 mt-10 xl:my-32">
      <h1 :class="{'animate__animated animate__fadeInDown animate__delay-03s animate__fast': $route.hash === '#about_c'}">Are You Ready For The Digital Age?</h1>
      <p :class="{'animate__animated animate__fadeInDown animate__delay-03s animate__fast': $route.hash === '#about_c'}">Join our community to start networking and learning. Join our public telegram with the link below.</p>
      <a :class="{'animate__animated animate__fadeInDown animate__delay-1s animate__fast': $route.hash === '#about_c'}"  href="http://community.progenius.io" target="_blank"><button class="py-3 px-10 flex gap-5 mt-16 items-center justify-between rounded-full transition bg-indigo-700 hover:bg-indigo-500 text-white font-bold">Join our community</button></a>
    </div>
    <div class="w-full" style="filter:invert(1)">
      <video autoplay muted loop class="w-full max-w-3xl block m-auto relative mt-10 xl:float-right" src="/an3.mp4" loading="lazy"></video>
    </div>
  </section>
</template>
