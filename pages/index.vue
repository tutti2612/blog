<template>
  <div>
    <div v-for="article in articles" class="h-8 border-b border-gray-300 mb-2">
      <nuxt-link :to="article.path">{{ article.title }}</nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  components: {},
  async asyncData({ $content }) {
    const articles = await $content("articles")
      .limit(5)
      .fetch();

    return {
      articles
    };
  }
};
</script>
