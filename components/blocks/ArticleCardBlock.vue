<template>
  <div class="w-1/2">
    <nuxt-link
      :to="{
        name: 'articles-username-article',
        params: { username: article.user.username, article: article.id },
      }"
      tag="article"
    >
      <div class="image-wrapper">
        <img
          v-if="article.cover_image"
          :src="article.cover_image"
          :alt="article.title"
        />
        <img v-else :src="article.social_image" :alt="article.title" />
      </div>
      <div class="content">
        <nuxt-link
          :to="{
            name: 'articles-username-article',
            params: { username: article.user.username, article: article.id },
          }"
        >
          <h1>{{ article.title }}</h1>
        </nuxt-link>
        <div class="tags">
          <nuxt-link
            v-for="tag in article.tag_list"
            :key="tag"
            :to="{ name: 'articles-t-tag', params: { tag } }"
            class="tag"
          >
            <span
              class="
                inline-flex
                items-center
                px-2.5
                py-0.5
                rounded-full
                font-medium
                bg-white
                text-black
              "
            >
              <svg
                class="-ml-0.5 mr-1.5 h-2 w-2 text-black"
                fill="currentColor"
                viewBox="0 0 8 8"
              >
                <circle cx="4" cy="4" r="3" />
              </svg>
              #{{ tag }}
            </span>
          </nuxt-link>
        </div>
        <div class="meta">
          <div class="scl">
            <span>
              <heart-icon />

              {{ article.positive_reactions_count }}
            </span>
            <span>
              <comments-icon />
              {{ article.comments_count }}
            </span>
          </div>
          <time>
            <span
              class="
                inline-flex
                items-center
                px-2.5
                py-0.5
                rounded-full
                text-xs
                font-medium
                bg-gray-100
                text-gray-800
              "
            >
              {{ article.readable_publish_date }}
            </span></time
          >
        </div>
      </div>
    </nuxt-link>
  </div>
</template>

<script>
import HeartIcon from '@/assets/icons/heart.svg?inline'
import CommentsIcon from '@/assets/icons/comments.svg?inline'
export default {
  components: {
    HeartIcon,
    CommentsIcon,
  },
  props: {
    article: {
      type: Object,
      default: null,
    },
  },
}
</script>

<style scoped>
article {
  border-radius: 1rem;
  overflow: hidden;
  cursor: pointer;
}
article .image-wrapper {
  position: relative;
  padding-bottom: 56.25%;
}
article .image-wrapper img {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
}
article .content {
  background: #666;
  padding: 1rem;
}
article .content h1 {
  margin-bottom: 1rem;
}
article .content .tags {
  display: flex;
  flex-wrap: wrap;
  margin-bottom: 0.5rem;
}
article .content .tags .tag {
  line-height: 1;
  padding: 0.5rem 0.5rem;
  margin: 0 0.5rem 0.5rem 0;
  border-radius: 0.25rem;
}
article .content .tags .tag:active {
  background: transparent;
}
article .content .meta {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
article .content .meta .scl {
  display: flex;
}
article .content .meta .scl span {
  display: flex;
  align-items: center;
  margin-right: 1rem;
}
article .content .meta .scl span svg {
  margin-right: 0.25rem;
}
</style>
