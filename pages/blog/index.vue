<template>
  <div>
    <h1>Blog Posts</h1>
    <div class="flex">
      <div v-for="article of articles" :key="article.slug" class="w-3/4">
        <NuxtLink :to="{ name: 'blog-slug', params: { slug: article.slug } }">
          <div class="flex border">
            <img :src="article.img" class="w-1/12 h-16 mr-4"/>
            <div>
              <h2 class="">{{ article.title }}</h2>
              <p class="">{{ article.description }}</p>
              <p class="">Written by : {{ article.author.name }}</p>
            </div>
          </div>
        </NuxtLink>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    async asyncData({ $content, params }) {
      const articles = await $content('articles').fetch()

      return {
        articles
      }
    }
  }
  
</script>