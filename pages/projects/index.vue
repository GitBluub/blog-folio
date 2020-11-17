<template>
    <div>
        <h1 class="mb-12 mt-5 text-center text-xl md:text-2xl lg:text-3xl xl:text-4xl">Some projects I have done</h1>
        <div class="flex flex-wrap w-full">
            <div v-for="project in projects" :key="project.slug" class="pl-5 pr-5 lg:pr-10 pb-12 w-full lg:w-1/2">
                <div class="border rounded flex-shrink-0 text-left flex h-full w-full">
                    <img v-if="project.thumbnail" class="rounded h-full" src="incredible_putin.png"/>
                    <img v-else class="rounded h-24" src="github-logo.png"/>
                    <div class="pl-10 mt-2 w-4/5 flex flex-col flex-grow-0">
                        <h1 class="pb-5 text-left text-headline text-base sm:text-lg md:text-2xl lg:text-xl xl:text-2xl">{{ project.project_name }}</h1>
                        <p class="pb-2 text-left text-sm sm:text-base md:text-xl lg:text-lg xl:text-xl flex-grow">{{ project.description}}</p>
                        <div class="pb-2 flex">
                            <img v-for="tech in project.techs" :key="tech" class="w-1/12" :src=" 'devicons/' + svg_techs[tech]" />
                        </div>
                        <NuxtLink  class="border rounded-t pl-5 pr-5 hover:bg-button-bg hover:text-button text-sm sm:text-base md:text-xl lg:text-lg xl:text-xl" style="width:max-content" :to="{ name: 'projects-slug', params: { slug: project.slug } }">See more</NuxtLink>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
  export default {
    async asyncData({ $content, params }) {
      const projects = await $content('projects').fetch()
      const svg_techs = {
        'javascript': 'javascript/javascript-plain.svg',
        'c': 'c/c-plain.svg',
        'html': 'html5/html5-plain.svg',
        'css': 'css3/css3-plain.svg',
        'vuejs': 'vuejs/vuejs-original.svg'
      };
      return {
        projects,
        svg_techs
      }
    }
  }
</script>