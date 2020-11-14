<template>
  <div>
    <div class="flex justify-center flex-col h-full">
      <div class="md:flex justify-center">
        <img class="w-1/5 h-1/5 rounded-full" src="pp.jpg" />
        <div class="ml-10 flex flex-col justify-around">
          <nuxt-link to="/about" class="text-left text-4xl hover:text-white">About Me</nuxt-link>
          <nuxt-link to="/projects" class="text-left text-4xl hover:text-white">My Projects</nuxt-link>
          <nuxt-link to="/blog" class="text-left text-4xl hover:text-white">My Blog</nuxt-link>
        </div>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  layout: "no_header"
}
</script>