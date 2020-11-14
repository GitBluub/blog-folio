<template>
    <div>
        <h1 class="mb-16 mt-10 text-center text-4xl">Some projects I have done</h1>
        <div class="flex flex-wrap">
            <div v-for="(project, index) in projects" :key="project.slug" class="pl-10 pr-10 pb-20 lg:w-1/2">
                <div class="border rounded flex-shrink-0 text-left flex h-full w-full">
                    <img v-if="project.thumbnail" class="rounded h-full" src="incredible_putin.png"/>
                    <img v-else class="rounded h-24" src="github-logo.png"/>
                    <div class="pl-10 w-4/5 flex flex-col">
                        <h1 class="text-left text-base sm:text-lg md:text-2xl lg:text-xl xl:text-2xl">{{ project.project_name }}</h1>
                        <p class="text-left text-sm sm:text-base md:text-xl lg:text-lg xl:text-xl flex-grow">{{ project.description}}</p>
                        <div class="flex ">
                            <img v-for="tech in project.techs" :key="tech" class="w-1/12" :src="svg_techs[tech]" />
                        </div>
                        <NuxtLink  :to="{ name: 'projects-slug', params: { slug: project.slug } }">See more</NuxtLink>
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
      };
      return {
        projects,
        svg_techs
      }
    }
  }
</script>