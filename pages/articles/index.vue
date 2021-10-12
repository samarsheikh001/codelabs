<template>
  <div class="page-wrapper">
    <div class="p-8 w-full">
      <div class="bg-white flex items-center rounded-full shadow-xl">
        <input
          class="
            rounded-l-full
            w-full
            px-6
            text-gray-700
            leading-tight
            focus:outline-none
          "
          v-model="search"
          id="search"
          type="text"
          placeholder="Search"
        />

        <div class="p-4">
          <button
            class="
              bg-black
              text-white
              rounded-full
              hover:bg-gray-600
              focus:outline-none
              w-12
              h-12
              flex
              items-center
              justify-center
            "
            @click="searchQuery"
          >
            icon
          </button>
        </div>
      </div>
    </div>

    <template v-if="$fetchState.pending">
      <div class="article-cards-wrapper">
        <content-placeholders
          v-for="p in 30"
          :key="p"
          rounded
          class="article-card-block"
        >
          <content-placeholders-img />
          <content-placeholders-text :lines="3" />
        </content-placeholders>
      </div>
    </template>
    <template v-else-if="$fetchState.error">
      <p>{{ $fetchState.error.message }}</p>
    </template>
    <template v-else>
      <div class="article-cards-wrapper">
        <article-card-block
          v-for="(article, i) in articles"
          :key="article.id"
          v-observe-visibility="
            i === articles.length - 1 ? lazyLoadArticles : false
          "
          :article="article"
          class="article-card-block"
        />
      </div>
    </template>
  </div>
</template>

<script>
import ArticleCardBlock from '@/components/blocks/ArticleCardBlock.vue'

export default {
  components: {
    ArticleCardBlock,
  },
  data() {
    return {
      currentPage: 1,
      search: 'flutter',
      articles: [],
    }
  },
  async fetch() {
    const articles = await fetch(
      `https://dev.to/api/articles?tag=${this.search}&state=rising&page=${this.currentPage}`
    ).then((res) => res.json())
    this.articles = this.articles.concat(articles)
  },
  methods: {
    async searchQuery() {
      const articles = await fetch(
        `https://dev.to/api/articles?tag=${this.search}&state=rising&page=1`
      ).then((res) => res.json())
      this.articles = articles
    },
    lazyLoadArticles(isVisible) {
      if (isVisible) {
        if (this.currentPage < 5) {
          this.currentPage++
          this.$fetch()
        }
      }
    },
  },
}
</script>

<style scoped>
.page-wrapper {
  margin: auto;
  padding: 1rem;
  min-height: 100vh;
  @apply container mx-auto;
}
.article-cards-wrapper {
  display: flex;
  flex-wrap: wrap;
  align-items: flex-start;
}
.article-cards-wrapper .article-card-block {
  width: calc(100% - 2 * 1rem);
  margin: 1rem;
  margin-bottom: 1.5rem;
  margin-top: 0.5rem;
}
@media (min-width: 640px) {
  .article-cards-wrapper .article-card-block {
    width: calc(50% - 2 * 1rem);
  }
}
@media (min-width: 1024px) {
  .article-cards-wrapper .article-card-block {
    width: calc(33.33333% - 2 * 1rem);
  }
}
</style>
