<template>
  <div>
    <div class="flex justify-center md:flex-col h-full text-center">
      <div class="flex flex-col md:flex-row justify-center w-1/2 md:w-full">
        <img class="md:w-1/5 md:h-1/5 rounded-full" src="pp.jpg" />
        <div class="md:ml-10 flex flex-col justify-around text-center md:text-left">
          <nuxt-link to="/about" class="text-4xl sm:text-5xl md:text-4xl lg:text-5xl xl:text-6xl hover:text-white">About Me</nuxt-link>
          <nuxt-link to="/projects" class="text-4xl sm:text-5xl md:text-4xl lg:text-5xl xl:text-6xl hover:text-white">My Projects</nuxt-link>
          <nuxt-link to="/blog" class="text-4xl sm:text-5xl md:text-4xl lg:text-5xl xl:text-6xl hover:text-white">My Blog</nuxt-link>
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