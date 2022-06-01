<template>
  <div id="research" class="w-full bg-white min-h-screen py-32">
    <Navigation class="fixed top-0 left-0" />

    <div class="p-5 lg:pl-32 lg:pr-20">
      <div>
        <h1 class="font-bold text-3xl mb-10 text-black">Research</h1>
        <img src="/effect.gif" alt="" />
      </div>
      <div class="grid">
        <nuxt-link
          :to="{ name: 'articles-slug', params: { slug: article.id } }"
          v-for="(article, index) in articles"
          :key="index"
          class="card border border-gray-300 transition rounded-md overflow-hidden cursor-pointer bg-white hover:shadow-lg"
        >
          <div class="snapshop-image">
            <img :src="article.snapshot" />
          </div>
          <div class="p-5">
            <h1 class="font-bold text-black text-lg mb-5 text-uppercase">
              {{ article.title }}
            </h1>
            <p class="desc text-gray-600">
              {{ article.description }}
            </p>
          </div>
        </nuxt-link>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data: function () {
    return {
      articles: [],
    }
  },
  mounted: function () {
    this.fetchArticles()
  },
  methods: {
    async fetchArticles() {
      const request = await this.$axios.$get(
        'https://progenius-be.herokuapp.com/api/snapshot/all'
      )
      this.articles = request.snapshots
    },
  },
}
</script>
<style scoped>
.grid {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr;
  grid-gap: 20px;
}
@media (max-width: 1200px) {
  .grid {
    grid-template-columns: 1fr 1fr;
  }
}
@media (max-width: 600px) {
  .grid {
    grid-template-columns: 1fr;
  }
}
.snapshop-image {
  height: 150px;
  width: 100%;
  background-color: black;
  overflow: hidden;
  display: flex;
  align-items: center;
}
.desc {
  overflow: hidden;
  text-overflow: ellipsis;
  display: -webkit-box;
  -webkit-line-clamp: 2; /* number of lines to show */
  line-clamp: 2;
  -webkit-box-orient: vertical;
}
</style>
