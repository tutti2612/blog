<template>
  <div>
    <nuxt-content :document="article" />
  </div>
</template>

<script>
import "@/assets/css/github-markdown.css";
export default {
  async asyncData({ $content, params }) {
    const article = await $content(`articles/${params.slug}`).fetch();

    return {
      article
    };
  }
};
</script>
