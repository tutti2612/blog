<template>
  <div>
    <nuxt-content :document="article" />
  </div>
</template>

<script>
export default {
  components: {},
  async asyncData({ $content, params }) {
    const article = await $content(`articles/${params.slug}`).fetch();

    return {
      article
    };
  }
};
</script>
