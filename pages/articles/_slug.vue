<template>
  <div class="w-full relative min-h-screen bg-white text-black">
    <Navigation />
    <div class="p-5 w-full lg:w-1/2 m-auto py-32">
      <h1 class="mb-16 text-6xl font-bold">{{ this.article.title }}</h1>
      <article v-html="this.article.summary"></article>
    </div>
  </div>
</template>
<script>
export default {
  data: function () {
    return {
      article: '',
    }
  },
  mounted: function () {
    this.fetchArticle(this.$route.params.slug)
  },
  methods: {
    async fetchArticle(slug) {
      const request = await this.$axios.$get(
        'https://progenius-be.herokuapp.com/api/snapshot/' + slug
      )
      this.article = request.snapshot
    },
  },
}
</script>
<style>
html {
  overflow: unset !important;
}
</style>
