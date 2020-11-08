<template>
  <div class="flex justify-between">
    <div class="flex flex-col pl-1 pr-10">
      <p> Previous Post: </p>
      <NuxtLink
        v-if="prev"
        :to="{ name: 'blog-slug', params: { slug: prev.slug } }"
        class="text-primary font-bold hover:underline">
        {{ prev.title }}
      </NuxtLink>
    </div>
    <div class="flex flex-col p-1">
      <p> Next Post: </p>
      <NuxtLink
        v-if="next"
        :to="{ name: 'blog-slug', params: { slug: next.slug } }"
        class="font-bold hover:underline">
        {{ next.title }}
      </NuxtLink>
    </div>
  </div>
</template>

<script>
  export default {
    props: {
      prev: {
        type: Object,
        default: () => null
      },
      next: {
        type: Object,
        default: () => null
      }
    }
  }
</script>
