<template>
  <header
    class="w-full z-40 py-5 lg:py-10 bg-black lg:bg-transparent px-5 lg:pl-32 lg:pr-20"
    :class="{
      light:
        ['#about', '#faqs', '#about_c'].indexOf($route.hash) > -1 ||
        $route.name === 'Research' ||
        $route.name === 'articles-slug',
    }"
  >
    <div class="flex justify-between items-center">
      <nuxt-link
        to="/"
        v-if="$route.name === 'Research' || $route.name === 'articles-slug'"
        class="logo flex items-center gap-3 font-bold text-lg"
      >
        <img width="64" src="/black_logo.png" alt="Progenius logo" />
        <span class="text-black">ProfessionalGenius</span>
      </nuxt-link>
      <div
        v-if="($route.name === 'index' && $route.hash === '') || !isNotMobile"
        class="logo flex items-center gap-3 font-bold text-lg"
      >
        <img width="64" src="/logo.png" alt="Progenius logo" />
        <span>ProfessionalGenius</span>
      </div>
      <nav class="hidden lg:flex gap-7">
        <NuxtLink class="text-gray-500" to="/">Home</NuxtLink>
        <NuxtLink
          class="text-gray-500"
          to="/#about"
          :class="{
            'nuxt-link-exact-active ':
              ['#about_b', '#about_c'].indexOf(this.$route.hash) > -1,
          }"
          >About</NuxtLink
        >
        <NuxtLink class="text-gray-500" to="/#pricing">Pricing</NuxtLink>
        <NuxtLink class="text-gray-500" to="/research">Research</NuxtLink>
        <NuxtLink class="text-gray-500" to="/#faqs">FAQs</NuxtLink>
        <NuxtLink class="text-gray-500" to="/#contact">Contact</NuxtLink>
        <!-- <NuxtLink class="text-gray-500" to="/pn">Private Network</NuxtLink> -->
        <!--<NuxtLink class="text-gray-500" to="/education">Education</NuxtLink> -->
      </nav>
      <div class="cta relative">
        <button
          class="hidden lg:flex py-3 px-10 items-center gap-5 text-black font-bold rounded-full bg-indigo-700 text-white hover:bg-indigo-500"
        >
          <img width="32" src="/metamask.svg" />
          <span>Lunch App</span>
        </button>
      </div>
      <button class="block lg:hidden" @click="showMobileMenu = true">
        <!-- prettier-ignore -->
        <svg fill="white"  xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"><path d="M24 6h-24v-4h24v4zm0 4h-24v4h24v-4zm0 8h-24v4h24v-4z"/></svg>
      </button>
      <div
        v-if="showMobileMenu"
        class="mobile fixed z-50 top-0 right-0 w-full h-screen m-auto p-16 bg-black text-white"
      >
        <span
          @click="showMobileMenu = false"
          class="float-right cursor-pointer text-xl font-bold"
          >X Close
        </span>
        <nav class="flex items-center h-full">
          <div class="flex flex-col w-full text-center">
            <NuxtLink class="text-3xl mb-10 text-gray-500" to="/"
              >Home</NuxtLink
            >
            <NuxtLink
              class="text-3xl mb-10 text-gray-500"
              to="/#about"
              :class="{
                'nuxt-link-exact-active ':
                  ['#about_b', '#about_c'].indexOf(this.$route.hash) > -1,
              }"
              >About</NuxtLink
            >
            <NuxtLink class="text-3xl mb-10 text-gray-500" to="/#pricing"
              >Pricing</NuxtLink
            >
            <NuxtLink class="text-3xl mb-10 text-gray-500" to="/research"
              >Research</NuxtLink
            >
            <NuxtLink class="text-3xl mb-10 text-gray-500" to="/#faqs"
              >FAQs</NuxtLink
            >
            <NuxtLink class="text-3xl mb-10 text-gray-500" to="/#contact"
              >Contact</NuxtLink
            >
          </div>
        </nav>
      </div>
    </div>
  </header>
</template>
<script>
export default {
  data: function () {
    return {
      showMobileMenu: false,
      isNotMobile: false,
    }
  },
  mounted: function () {
    this.isNotMobile = window.innerWidth > 600
  },
  watch: {
    $route(to, from) {
      this.showMobileMenu = false
    },
  },
}
</script>
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

header .mobile a {
  color: #ddd;
  transition: color ease-in-out 1s;
}
header .mobile a.nuxt-link-exact-active {
  font-weight: 800;
  color: white;
}
</style>
