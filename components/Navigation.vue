<template>
  <header
    class="w-full py-10 bg-transparent"
    :class="{
      light: ['#about', '#faqs'].indexOf($route.hash) > -1,
    }"
  >
    <div class="container m-auto flex justify-between items-center">
      <div
        v-if="!$route.hash"
        class="logo flex items-center gap-3 font-bold text-lg"
      >
        <img width="64" src="/logo.png" alt="Progenius logo" />
        <span>ProfessionalGenius</span>
      </div>
      <nav class="flex gap-7">
        <NuxtLink class="text-gray-500" to="/">Home</NuxtLink>
        <NuxtLink class="text-gray-500" to="#about">About</NuxtLink>
        <NuxtLink class="text-gray-500" to="#pricing">Pricing</NuxtLink>
        <NuxtLink class="text-gray-500" to="/research">Research</NuxtLink>
        <NuxtLink class="text-gray-500" to="#faqs">FAQs</NuxtLink>
        <NuxtLink class="text-gray-500" to="#contact">Contact</NuxtLink>
        <!-- <NuxtLink class="text-gray-500" to="/pn">Private Network</NuxtLink> -->
        <!--<NuxtLink class="text-gray-500" to="/education">Education</NuxtLink> -->
      </nav>
      <div class="cta">
        <button
          class="flex py-3 px-10 items-center gap-5 text-black font-bold rounded-full bg-indigo-700 text-white hover:bg-indigo-500"
        >
          <img width="32" src="/metamask.svg" />
          <span>Login with Metamask</span>
        </button>
      </div>
    </div>
  </header>
</template>
<style scoped>
header a {
  color: #ddd;
  transition: color ease-in-out 1s;
}
header a.nuxt-link-exact-active {
  font-weight: 800;
  color: white;
}
header.light a {
  color: #333;
}
header.light a.nuxt-link-exact-active {
  font-weight: 800;
  color: black;
}
</style>
