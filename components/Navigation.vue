<template>
  <!-- prettier-ignore -->
  <header class="w-full z-30 p-5 flex justify-between items-center lg:pl-32 lg:pr-20" :class="{'flex-row-reverse lg:flex-row': !showLogo}">
    <div v-if="showLogo" class="brand flex items-center gap-3">
      <nuxt-link v-if="$route.name === 'Research' || $route.name === 'articles-slug'" to="/"><img  width="64" src="/black_logo.png" alt="" /></nuxt-link>
      <nuxt-link  v-else to="/"><img width="64" src="/logo.png" alt="" /></nuxt-link>
      <span class="hidden lg:block text-xl font-bold" :class="($route.name === 'Research' || $route.name === 'articles-slug') ? 'text-black':'text-white'">ProfessionalGenius</span>
    </div>
    <nav class="navigation-menu gap-7" :class="{ light: ['#about', '#faqs', '#about_c'].indexOf($route.hash) > -1 || $route.name === 'Research' || $route.name === 'articles-slug' }">
      <NuxtLink to="/">Home</NuxtLink>
      <NuxtLink to="/#about" :class="{ 'nuxt-link-exact-active': ['#about_b', '#about_c'].indexOf(this.$route.hash) > -1, }">About</NuxtLink>
      <NuxtLink to="/#pricing">Pricing</NuxtLink>
      <a href="http://community.progenius.io">Community</a>
      <NuxtLink to="/#faqs">FAQs</NuxtLink>
      <NuxtLink to="/#contact">Contact</NuxtLink>
    </nav>
    <a href="http://community.progenius.io" class="cta py-3 px-10  gap-5 items-center justify-between rounded-full transition bg-indigo-700 hover:bg-indigo-500 text-white font-bold">
      <span>Join community</span>
    </a>
    <button @click="showMobileMenu = !showMobileMenu" class="burger z-40 bg-white p-2 rounded-full drop-shadow-xl">
      <svg v-if="showMobileMenu" fill="black" width="32" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" class="eva eva-close-outline"><g data-name="Layer 2"><g data-name="close"><rect width="24" height="24" transform="rotate(180 12 12)" opacity="0"></rect><path d="M13.41 12l4.3-4.29a1 1 0 1 0-1.42-1.42L12 10.59l-4.29-4.3a1 1 0 0 0-1.42 1.42l4.3 4.29-4.3 4.29a1 1 0 0 0 0 1.42 1 1 0 0 0 1.42 0l4.29-4.3 4.29 4.3a1 1 0 0 0 1.42 0 1 1 0 0 0 0-1.42z"></path></g></g></svg>
      <svg v-else fill="black" width="32" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" class="eva eva-menu-outline" ><g data-name="Layer 2"><g data-name="menu"><rect width="24" height="24" transform="rotate(180 12 12)" opacity="0"></rect><rect x="3" y="11" width="18" height="2" rx=".95" ry=".95"></rect><rect x="3" y="16" width="18" height="2" rx=".95" ry=".95"></rect><rect x="3" y="6" width="18" height="2" rx=".95" ry=".95"></rect></g></g></svg>
    </button>
    <div v-if="showMobileMenu" class="mobile fixed z-30 top-0 right-0 w-full h-screen m-auto p-16 bg-black text-white flex items-center">
      <nav class="mobile flex flex-col w-full text-center">
        <NuxtLink to="/">Home</NuxtLink>
        <NuxtLink to="/#about" :class="{ 'nuxt-link-exact-active': ['#about_b', '#about_c'].indexOf(this.$route.hash) > -1, }">About</NuxtLink>
        <NuxtLink to="/#pricing">Pricing</NuxtLink>
        <a href="http://community.progenius.io">Community</a>
        <NuxtLink to="/#faqs">FAQs</NuxtLink>
        <NuxtLink to="/#contact">Contact</NuxtLink>
      </nav>
    </div>
  </header>
</template>
<script>
export default {
  data: function () {
    return {
      showLogo: true,
      showMobileMenu: false,
    }
  },
  mounted: function () {
    this.showLogo = window.scrollY < 100
    window.addEventListener('scroll', this.updateShowLogo)
  },
  watch: {
    $route(to, from) {
      this.showMobileMenu = false
    },
  },
  methods: {
    updateShowLogo: function (e) {
      this.showLogo = e.path[1].scrollY < 100
    },
  },
}
</script>
<style scoped>
nav a {
  color: #ddd;
  transition: color ease-in-out 1s;
}
nav a.nuxt-link-exact-active {
  font-weight: 800;
  color: white;
}
nav.light a {
  color: #333;
}
nav.light a.nuxt-link-exact-active {
  font-weight: 800;
  color: black;
}
nav.mobile a {
  color: #ddd;
  font-size: 24px;
  font-weight: normal;
  margin-bottom: 20px;
}
nav.mobile a.nuxt-link-exact-active {
  color: white;
  font-weight: bold;
}
.cta {
  display: flex
}
.burger {
  display: none
}
.navigation-menu {
  display: flex
}
@media (max-width: 1320px) { 
  .navigation-menu {
    display: none
  }
  .burger{
    display: flex
  }
  .cta {
    display: none
  }
}

</style>
