<template>
  <div
    id="pricing"
    class="bg-black text-white flex items-center py-32 px-5 min-h-screen lg:px-32"
  >
    <div class="relative w-full">
      <h1 :class="{'animate__animated animate__fadeInDown animate__delay-03s animate__fast': $route.hash === '#pricing'}" class="text-6xl font-bold mb-20 blurred">Choose your pricing plan</h1>
      <div class="plans block lg:flex lg:gap-5 items-center relative">
        <div
          class="bg-red w-full absolute h-screen flex items-center z-10 text-4xl opacity-75 font-bold text-center"
        ></div>
        <div class="plan blurred bg-gray-900 rounded-xl p-10 w-full lg:w-1/3" :class="{'animate__animated animate__fadeInDown animate__delay-1s animate__faster': $route.hash === '#pricing'}">
          <h1 class="font-bold text-2xl mb-5">Premium Group</h1>
          <p class="mb-5">
            Trades/ Early Gems, Tips for passive income, Top Giveaways
          </p>
          <p class="text-2xl font-bold">$19.99</p>
          <button
            class="transition mt-10 py-5 px-10 bg-white text-black font-bold rounded-full hover:bg-gray-200"
          >
            Select plan
          </button>
        </div>
        <div class="plan blurred bg-indigo-900 rounded-xl p-10 w-full lg:w-1/3" :class="{'animate__animated animate__fadeInDown animate__delay-2s animate__faster': $route.hash === '#pricing'}">
          <h1 class="font-bold text-2xl mb-5">Premium Group</h1>
          <p class="mb-5">
            Trades/ Early Gems, Tips for passive income, Top Giveaways
          </p>
          <p class="text-2xl font-bold">$19.99</p>
          <button
            class="transition mt-10 py-5 px-10 bg-white text-black font-bold rounded-full hover:bg-gray-200"
          >
            Select plan
          </button>
        </div>
        <div class="plan blurred bg-yellow-900 rounded-xl p-10 w-full lg:w-1/3" :class="{'animate__animated animate__fadeInDown animate__delay-3s animate__faster': $route.hash === '#pricing'}">
          <h1 class="font-bold text-2xl mb-5">Premium Group</h1>
          <p class="mb-5">
            Trades/ Early Gems, Tips for passive income, Top Giveaways
          </p>
          <p class="text-2xl font-bold">$19.99</p>
          <button
            class="transition mt-10 py-5 px-10 bg-white text-black font-bold rounded-full hover:bg-gray-200"
          >
            Select plan
          </button>
        </div>
      </div>
    </div>
  </div>
</template>
<style scoped>
.blurred {
  filter: blur(10px);
}
</style>
