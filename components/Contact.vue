<template>
  <div
    id="contact"
    class="contact w-full bg-black text-white flex items-center h-screen"
  >
    <div class="container m-auto flex items-center justify-between">
      <div class="hero w-1/3">
        <div class="content">
          <h1 class="text-6xl font-bold">Get in touch.</h1>
          <p class="mt-10 text-lg text-gray-300">
            If you are as curious as we are, building something interesting that
            the space needs, and looking for a partner who will strive to make
            it a success, get in touch. We'd love to collaborate.
          </p>
          <div class="actions flex gap-5">
            <button
              class="transition mt-10 py-5 px-10 font-bold rounded-full bg-indigo-700 text-white hover:bg-indigo-500"
            >
              Contact us
            </button>
          </div>
        </div>
      </div>
      <img src="/dark-animation.gif" alt="" />
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
