<template>
  <div>
    <h1 class="text-center text-2xl sm:text-3xl md:text-4xl lg:text-5xl xl:text-6xl">Recently published</h1>
    <div class="">
      <div v-for="(article, index) in articles" :key="article.slug" class="flex w-full px-4 pb-10">
        <NuxtLink :to="{ name: 'blog-slug', params: { slug: article.slug } }">
          <div 
            @mouseover="hover = index"
            @mouseleave="hover = -1">
            <h2 class="text-xl sm:text-2xl md:text-3xl lg:text-4xl xl:text-5xl text-left" :class="{ activeTitle: hover == index}">{{ article.title }}</h2>
            <p class="text-md sm:text-lg md:text-xl lg:text-2xl xl:text-3xl text-left" :class="{ activeDesc: hover == index}">{{ article.description }}</p>
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