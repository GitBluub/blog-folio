<template>
  <article>
    <!-- Search blog posts component
    <AppSearchInput />
    <h1>{{ article.title }}</h1>
    <nav>
      <!-- TABLE OF CONTENT
      <h1 class="text-left"> Table of content: </h1>
      <ul class="">
        <li class="underline" v-for="link of article.toc" :key="link.id">
          <NuxtLink :to="`#${link.id}`" :class="{ 'py-2': link.depth === 2, 'ml-2 pb-2': link.depth === 3 }">{{ link.text }}</NuxtLink>
        </li>
      </ul>
      -->
    </nav>
    <p class="desc">{{ article.description }}</p>
    <!-- img of the article
    <div class="text-center">
      <img class="inline" :src="article.img" :alt="article.alt" />
    </div>
    -->
    <nuxt-content :document="article" />
    <p>Post last updated: {{ formatDate(article.updatedAt) }}</p>
    <!-- Author component
    <author :author="article.author"></author>
    -->
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