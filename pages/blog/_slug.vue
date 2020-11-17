<template>
  <article>
    <nuxt-content :document="article" />
    <p>Post last updated: {{ formatDate(article.updatedAt) }}</p>
    <prev-next :prev="prev" :next="next" />
  </article>
</template>

<script>
  export default {
    async asyncData({ $content, params }) {
      const article = await $content('articles', params.slug).fetch()
      const [prev, next] = await $content('articles')
      .only(['title', 'slug'])
      .sortBy('createdAt', 'asc')
      .surround(params.slug)
      .fetch()

      return {
        article,
        prev,
        next
      }
    },
    methods: {
      formatDate(date) {
        const options = { year: 'numeric', month: 'long', day: 'numeric' };
        return new Date(date).toLocaleDateString('en', options);
      }
    }
  }
  
</script>

<style>
.nuxt-content h1 {
  font-weight: bold;
  font-size: 40px;
}

.nuxt-content h2 {
  font-weight: bold;
  font-size: 28px;
}
.nuxt-content h3 {
  font-weight: bold;
  font-size: 22px;
}
.nuxt-content p {
  margin-bottom: 20px;
}
.desc {
  color: #a7a9be;
}
h1, h2, h3, p, a {
  text-align: center;
}
</style>