<template>
    <projectPage>
      <h1 class="text-center text-6xl text-headline"> {{ project.project_name }} </h1>
      <nuxt-content :document="project" />
    </projectPage>
</template>

<script>
  export default {
    async asyncData({ $content, params }) {
      const project = await $content('projects', params.slug).fetch()
      return {
        project
      }
    }
  }
</script>