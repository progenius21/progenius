<template>
  <div
    id="home"
    class="home w-full bg-gif py-32 flex items-center overflow-hidden h-screen lg:px-32"
  >
    <div class="z-10 w-full m-auto px-5 lg:w-8/12">
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
            Launch App
          </button>
          <button
            class="transition mt-10 py-5 px-10 bg-transparent text-white font-medium rounded-full hover:font-bold"
          >
            Learn more
          </button>
        </div>
        <div class="mt-16 block lg:hidden">
          <p>
            "Don't let your learning lead to knowledge, let your learning lead
            to action."
          </p>
          <p>Jim Rohn</p>
        </div>
      </div>
      <div class="hidden lg:block quote">
        <p>
          "Don't let your learning lead to knowledge, let your learning lead to
          action."
        </p>
        <p>Jim Rohn</p>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data: function () {
    return {
      isNotMobile: false,
    }
  },
  mounted: function () {
    this.isNotMobile = window.innerWidth > 600
  },
}
</script>
<style scoped>
.bg-gif {
  background-image: url('/bg.gif');
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
}

.bg-gif::before {
  content: '';
  padding: 7%;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: absolute;
  top: 0%;
  left: 0;
}

.quote {
  position: absolute;
  bottom: 150px;
  right: 100px;
}
</style>
