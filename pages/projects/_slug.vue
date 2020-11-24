<template>
    <projectPage>
      <nuxt-content class="ml-6" id="content" :document="project" />
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

<style>
#content h1{
  font-size:  3.75rem;
  text-align: center;
  color: #fffffe;
  margin-bottom: 20px;
}
#content h2{
  font-size:  3rem;
  color: #fffffe;
  margin-bottom: 10px;
}
#content a {
  color: #fffffe;
}
#content a:hover {
  color: #ff8906;
}
#content {
  font-size: 1.5rem;
} 
</style>