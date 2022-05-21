<template>
  <div
    id="education"
    class="education bg-gif w-full p-10 h-screen bg-black text-white flex items-center"
  >
    <div>
      <h1 class="text-6xl font-bold">Education</h1>
      <div class="flex row gap-5 mt-10">
        <div
          v-for="n in 5"
          :key="n"
          class="border border-1 border-gray-500 rounded-3xl overflow-hidden hover:border-white cursor-pointer"
        >
          <img
            src="https://img.youtube.com/vi/m5WUPoP-RZM/hqdefault.jpg"
            alt=""
          />
          <p class="font-bold text-2xl pb-10 px-5 bg-red">Lorem Ipsum</p>
        </div>
      </div>
    </div>
  </div>
</template>
<style scoped>
.bg-gif {
  /* background-image: url('/bg-dark.jpg'); */
  background-repeat: no-repeat;
  background-position: center;
  background-color: black;
  background-blend-mode: difference;
}
</style>
