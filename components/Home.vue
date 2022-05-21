<template>
  <div id="home" class="home w-full bg-gif p-10 h-screen flex">
    <div class="container m-auto flex items-center">
      <div class="hero w-2/3 m-auto">
        <div class="content">
          <h1 class="text-6xl font-bold">Introducing Web3.0, Simply.</h1>
          <p class="mt-10 text-base text-gray-300">
            We are more than just investors. We are a group of highly-skilled,
            result-orientated individuals from various professional backgrounds
            all working towards educating and empowering our community.
          </p>
          <div class="actions flex gap-5">
            <button
              class="transition mt-10 py-5 px-10 font-bold rounded-full bg-indigo-700 text-white hover:bg-indigo-500"
            >
              Join our community
            </button>
            <button
              class="transition mt-10 py-5 px-10 bg-transparent text-white font-medium rounded-xl hover:bg-white hover:text-black"
            >
              Learn more
            </button>
          </div>
        </div>
        <div class="quote absolute right-10 z-10 bottom-32 float-right">
          <p>
            "Don't let your learning lead to knowledge, let your learning lead
            to action."
          </p>
          <p>Jim Rohn</p>
        </div>
      </div>
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
