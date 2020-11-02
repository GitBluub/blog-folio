<template>
  <div>
    <div class="bg-el-bg flex">
      <h1 class="text-5xl w-1/2 text-left">Louis "Bluub" Auzuret</h1>
      <div class="flex justify-end w-1/2">
        <nuxt-link to="/blog" class="text-2xl mr-16 hover:text-white">About me</nuxt-link>
        <nuxt-link to="/blog" class="text-2xl mr-16 hover:text-white">Projects</nuxt-link>
        <nuxt-link to="/blog" class="text-2xl mr-16 hover:text-white">Blog</nuxt-link>
      </div>
    </div>
  </div>
</template>

<style>
.title-head {
    background: #36D1DC;  /* fallback for old browsers */
    background: -webkit-linear-gradient(to right, #5B86E5, #36D1DC);  /* Chrome 10-25, Safari 5.1-6 */
    background: linear-gradient(to right, #5B86E5, #36D1DC); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
}
</style>