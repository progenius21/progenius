<template>
  <div
    id="about"
    class="about w-full bg-white text-black flex items-center h-screen"
  >
    <div class="container m-auto flex items-center justify-between">
      <div class="hero w-1/2">
        <div class="content">
          <h1 class="text-6xl font-bold">
            The world is digitising. <br />
            Web 3.0 is inevitable.
          </h1>
          <p class="mt-10 text-lg text-gray-700">
            Professional Genius aims to educate anyone and everyone, whatever
            their level of experience, about cryptocurrency and its importance.
            ProGenius also strives to provide top quality information for avid
            investors regarding high quality cryptocurrency projects at the
            earliest stages of their development.
          </p>
          <!-- <div class="actions flex gap-5">
            <button
              class="transition mt-10 py-5 px-10 bg-black text-white font-bold rounded-xl hover:bg-gray-900"
            >
              Join our community
            </button>
            <button
              class="transition mt-10 py-5 px-10 bg-transparent text-black border border-1 border-black font-bold rounded-xl hover:bg-black hover:text-white"
            >
              Learn more
            </button>
          </div> -->
        </div>
      </div>
      <img src="/light-animation.gif" alt="" />
    </div>
  </div>
</template>
<style scoped>
.scroll {
  position: absolute;
  transform: rotate(90deg);
  text-transform: uppercase;
}

.bg-gif {
  background-image: url('/bg.gif');
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
}
</style>
