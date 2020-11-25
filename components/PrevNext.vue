<template>
  <div class="flex justify-between">
    <div v-if="prev" class="flex flex-col pl-1 pr-10">
      <p class="text-left"> Previous Post: </p>
      <NuxtLink
        :to="{ name: 'blog-slug', params: { slug: prev.slug } }"
        class="text-primary font-bold hover:underline">
        {{ prev.title }}
      </NuxtLink>
    </div>
    <div v-if="next" class="flex flex-col p-1">
      <p class="text-left"> Next Post: </p>
      <NuxtLink
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
