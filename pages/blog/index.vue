<template>
  <div>
    <h1 class="text-center text-6xl">Recently published</h1>
    <div class="">
      <div v-for="(article, index) in articles" :key="article.slug" class="w-3/4">
        <div class="flex pb-10 pl-4">
          <NuxtLink :to="{ name: 'blog-slug', params: { slug: article.slug } }">
            <div 
              @mouseover="hover = index"
              @mouseleave="hover = -1">
              <h2 class="text-4xl text-left" :class="{ activeTitle: hover == index}">{{ article.title }}</h2>
              <p class="text-left" :class="{ activeDesc: hover == index}">{{ article.description }}</p>
              <!-- Possible "Written by" if multiple people write articles, useless in my case
              <p class="" :class="{ activeWrittenBy: hover == index}">Written by : {{ article.author.name }}</p>
              -->
            </div>
          </NuxtLink>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    async asyncData({ $content, params }) {
      const articles = await $content('articles').fetch()

      return {
        articles,
        hover: -1
      }
    }
  }
  
</script>

<style>
.activeTitle {
  color: #e53170;
}
</style>