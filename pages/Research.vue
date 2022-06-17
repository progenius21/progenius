<template>
  <div id="research" class="w-full bg-white min-h-screen py-32">
    <Navigation class="fixed top-0 left-0" />

    <div class="p-5 lg:pl-32 lg:pr-20">
      <div>
        <h1 class="font-bold text-3xl mb-10 text-black">Research</h1>
        <img src="/effect.gif" alt="" />
      </div>
      <div class="grid gap-10 mt-10 lg:gap-10 md:grid-cols-2 xl:grid-cols-3">
        <nuxt-link class="cursor-pointer group" :to="{ name: 'articles-slug', params: { slug: article.id } }" v-for="(article, index) in articles" :key="index">
          <div
            class="relative overflow-hidden transition-all bg-gray-100 rounded-md dark:bg-gray-800   hover:scale-105 aspect-square">
            <a href="/post/10-simple-practices-that-will-help-you-get-1-better-every-day"><span
                style="box-sizing: border-box; display: block; overflow: hidden; width: initial; height: initial; background: none; opacity: 1; border: 0px; margin: 0px; padding: 0px; position: absolute; inset: 0px;"><img
                  alt="Thumbnail" sizes="80vw"
                  :src="article.snapshot"
                  decoding="async" data-nimg="fill" class="transition-all"
                  style="position: absolute; inset: 0px; box-sizing: border-box; padding: 0px; border: none; margin: auto; display: block; width: 0px; height: 0px; min-width: 100%; max-width: 100%; min-height: 100%; max-height: 100%; object-fit: cover;"><noscript></noscript></span></a>
          </div>
          <h2 class="mt-2 text-lg font-semibold tracking-normal text-brand-primary text-black"><span
              class="text-black bg-gradient-to-r from-green-200 to-green-100 bg-[length:0px_10px] bg-left-bottom bg-no-repeat transition-[background-size] duration-500 hover:bg-[length:100%_3px] group-hover:bg-[length:100%_10px]">{{ article.title }}</span></h2>
          <div class="hidden">
            <p class="mt-2 text-sm text-gray-500 dark:text-gray-400 line-clamp-3"><a
                href="/post/10-simple-practices-that-will-help-you-get-1-better-every-day">{{ article.description }}</a></p>
          </div>
          <div class="flex items-center mt-3 space-x-3 text-gray-500 dark:text-gray-400">
            <div class="flex items-center w-full justify-between">
              <span class="text-sm">{{ article.author }}</span>
              <time class="text-sm mr-10" :datetime="article.createdAt">{{ new Date(article.createdAt).toLocaleDateString() }}</time>
            </div>
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
  grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
  grid-gap: 20px;
}
@media (max-width: 1600px) {
  .grid {
    grid-template-columns: 1fr 1fr 1fr 1fr;
  }
}
@media (max-width: 1200px) {
  .grid {
    grid-template-columns: 1fr 1fr 1fr;
  }
}
@media (max-width: 800px) {
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
