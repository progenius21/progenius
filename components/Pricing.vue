<template>
  <div
    id="pricing"
    class="bg-black text-white flex items-center py-32 px-5 min-h-screen lg:px-32"
  >
    <div class="relative z-10 w-full">
      <h1 class="text-6xl font-bold mb-20 blurred">Choose your pricing plan</h1>
      <div class="plans block lg:flex lg:gap-5 items-center relative">
        <p
          class="bg-red w-full absolute z-10 text-4xl opacity-75 font-bold text-center"
        >
          Coming soon
        </p>
        <div class="plan blurred bg-gray-900 rounded-xl p-10 w-full lg:w-1/3">
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
        <div class="plan blurred bg-indigo-900 rounded-xl p-10 w-full lg:w-1/3">
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
        <div class="plan blurred bg-yellow-900 rounded-xl p-10 w-full lg:w-1/3">
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
