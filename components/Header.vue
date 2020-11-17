<template>
  <div>
    <header class="px-5 flex flex-wrap items-center py-0">
      <div class="flex items-center w-auto" id="menu">
        <nuxt-link to="/" class="pt-0 ml-4 flex items-center justify-start mb-0 pointer-cursor">
          <img class="rounded-full w-10 lg:w-16 h-10 lg:h-16 border-2 border-transparent hover:border-button-bg" src="pp.jpg" alt="Andy Leverenz">
        </nuxt-link>
        <nav>
          <ul class="flex items-center justify-between text-base text-paragraph">
            <li><nuxt-link class="p-4 block border-b-2 border-transparent hover:border-button-bg text-xl md:text-2xl lg:text-3xl xl:text-4xl" to="/about" href="#">About Me</nuxt-link></li>
            <li><nuxt-link class="p-4 block border-b-2 border-transparent hover:border-button-bg text-xl md:text-2xl lg:text-3xl xl:text-4xl" to="/projects" href="#">Projects</nuxt-link></li>
            <li><nuxt-link class="p-4 block border-b-2 border-transparent hover:border-button-bg text-xl md:text-2xl lg:text-3xl xl:text-4xl" to="/blog" href="#">Blog</nuxt-link></li>
          </ul>
        </nav>
      </div>
    </header>
  </div>
</template>