<template>
  <!-- prettier-ignore -->
  <section id="home" class="w-full min-h-screen overflow-hidden py-32 px-5 lg:px-32 bg-gif flex flex-col lg:flex-row justify-between items-center">
    <div class="prose lg:prose-xl prose-invert z-10 mt-16 lg:mt-32">
      <h1>Introducing Web3.0, Simply<span class="text-indigo-700 ">.</span></h1>
      <p>We are more than just investors. We are a group of highly-skilled, result-orientated individuals from various professional backgrounds all working towards educating and empowering our community.</p>
      <!-- Actions -->
      <div class="actions flex gap-5 mt-16">
        <button class="px-5 py-3 flex gap-5 items-center justify-between rounded-full transition bg-indigo-700 hover:bg-indigo-500 text-white font-bold">
          <!-- prettier-ignore -->
          <svg width="32" fill="white" viewBox="0 0 30 30" xml:space="preserve" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"><polygon points="11,22 8,19 8,14 16,22 "/><path d="M26.979,3.021C26.979,3.021,18,3,11,10c-2.99,2.99-3,8-1,10s7.01,1.99,10-1C27,12,26.979,3.021,26.979,3.021z M17,11  c0-1.105,0.895-2,2-2c1.105,0,2,0.895,2,2s-0.895,2-2,2C17.895,13,17,12.105,17,11z"/><path d="M18.811,18.676c0,0,0.757,3.784-0.757,5.297C15.784,26.243,12,27,12,27l1-7L18.811,18.676z"/><path d="M11.324,11.189c0,0-3.784-0.757-5.297,0.757C3.757,14.216,3,18,3,18l7-1L11.324,11.189z"/><path d="M9.542,22.34c-0.045,0.064-0.072,0.138-0.13,0.195c-0.975,0.975-2.438,0.488-2.438,0.488s-0.488-1.463,0.488-2.438  c0.058-0.058,0.131-0.084,0.195-0.13L7.2,19.997c-0.38,0.1-0.741,0.29-1.038,0.587c-1.366,1.366-1.149,4.4-1.149,4.4  s3.016,0.235,4.4-1.149C9.71,23.538,9.9,23.177,10,22.797L9.542,22.34z"/></svg>
          <span>Launch App</span>
        </button>
        <nuxt-link to="#about" class="p-3 flex gap-5 items-center justify-between rounded-full transition-all bg-transparent text-gray-200 hover:text-white font-bold no-underline	">Learn more</nuxt-link>
      </div>
      <!-- End Actions -->
    </div>
    <div class="lg:h-full flex items-end mt-32">
      <div>
        <p class="text-lg">"Don't let your learning lead to knowledge, let your learning lead to action."</p>
        <p class="text-xl mt-3 font-bold">Jim Rohn</p>
      </div>
    </div>
  </section>
</template>
<style lang="css" scoped>
.bg-gif {
  background-image: url('/bg.gif');
  background-repeat: no-repeat;
  background-size: cover;
  background-position: 30%;
}
@media (max-width: 1000px) {
  .bg-gif {
    background-position: bottom;
  }
}
.bg-gif::before {
  content: '';
  padding: 7%;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.2);
  position: absolute;
  top: 0%;
  left: 0;
}
</style>
