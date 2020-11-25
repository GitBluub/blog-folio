<template>
  <article>
    <nuxt-content id="content" class="text-left" :document="article" />
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
#content h1{
  font-size:  3.75rem;
  text-align: center;
  color: #fffffe;
  margin-bottom: 20px;
}
#content h2{
  font-size:  3rem;
  color: #fffffe;
  margin-bottom: 10px;
}
.nuxt-content p {
  margin-bottom: 20px;
}

#content a {
  color: #fffffe;
}
#content a:hover {
  color: #ff8906;
}

.desc {
  color: #a7a9be;
}
</style>