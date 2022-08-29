<template>
  <!-- prettier-ignore -->
  <section id="about" class="w-full min-h-screen overflow-hidden px-5 lg:px-32 block flex flex-col-reverse xl:flex-row items-center justify-between text-dark relative" style="background-color:#fdfef3">
    <div class="prose xl:prose-md relative z-10 mb-32 mt-10 xl:my-32">
      <h1 :class="{'animate__animated animate__fadeInDown animate__delay-03s animate__fast': $route.hash === '#about'}">The world is digitising. <br />Web 3.0 is inevitable<span class="text-indigo-700 ">.</span></h1>
      <p :class="{'animate__animated animate__fadeInDown animate__delay-03s animate__fast': $route.hash === '#about'}">Professional Genius aims to educate anyone and everyone, whatever their level of experience, about cryptocurrency and its importance. ProGenius also strives to provide top quality information for avid investors regarding high quality cryptocurrency projects at the earliest stages of their development.</p>
      <a href="http://community.progenius.io" :class="{'animate__animated animate__fadeInDown animate__delay-1s animate__fast': $route.hash === '#about'}" to="/#contact"><button class="py-3 px-10 flex gap-5 mt-8 items-center justify-between rounded-full transition bg-indigo-700 hover:bg-indigo-500 text-white font-bold">Join community</button></a>
    </div>
    <div class="w-full" style="filter:invert(1)">
      <video controls="false" playsinline autoplay muted loop class="w-full max-w-3xl block m-auto relative mt-10 xl:float-right" loading="lazy">
         <source src="/an4.mp4" type="video/mp4">
      </video>
    </div>
  </section>
</template>

