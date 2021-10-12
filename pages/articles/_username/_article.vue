<template>
  <div class="page-wrapper">
    <div class="article-content-wrapper">
      <article-block class="article-block" />
      <div class="aside-username-wrapper">
        <aside-username-block class="aside-username-block" />
      </div>
    </div>
    <comments-block class="comments-block" />
  </div>
</template>

<script>
  import ArticleBlock from '@/components/blocks/ArticleBlock'
  import CommentsBlock from '@/components/blocks/CommentsBlock'
  import AsideUsernameBlock from '@/components/blocks/AsideUsernameBlock'

  export default {
    components: {
      ArticleBlock,
      CommentsBlock,
      AsideUsernameBlock
    }
  }
</script>


<style scoped>
.page-wrapper {
	 margin: auto;
	 padding: 1rem;
}
 .article-content-wrapper {
	 display: flex;
	 flex-direction: column;
	 align-items: center;
	 margin: auto;
	 margin-bottom: 2rem;
}
 .article-content-wrapper .article-block {
	 width: 100%;
	 max-width: 880px;
}
 .article-content-wrapper .aside-username-wrapper {
	 max-width: 880px;
	 width: 100%;
	 position: relative;
}
 .article-content-wrapper .aside-username-wrapper .aside-username-block {
	 position: sticky;
	 top: 1rem;
}
</style>