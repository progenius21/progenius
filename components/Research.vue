<template>
  <div id="research" class="w-full bg-black h-screen py-32">
    <div class="container m-auto">
      <div>
        <h1 class="font-bold text-3xl mb-10">Research</h1>
        <img src="/effect.gif" alt="" />
      </div>
      <div class="grid">
        <div
          v-for="(article, index) in articles"
          :key="index"
          class="card transition rounded-2xl overflow-hidden cursor-pointer bg-gray-900 hover:bg-indigo-900"
        >
          <div class="snapshop-image">
            <img :src="article.snapshot" />
          </div>
          <div class="p-5">
            <h1 class="font-bold text-lg mb-5 text-uppercase">
              {{ article.title }}
            </h1>
            <p class="desc">
              {{ article.description }}
            </p>
          </div>
        </div>
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
  grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
  grid-gap: 20px;
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
