<template lang="pug">
  .Repo(v-if="repo")
    .card.has-text-left
      .card-content
        p.title
          | {{repo.name}}
          //- (v-if="repo.")
        p.subtitle
          | {{repo.description}}
      footer.card-footer
        p.card-footer-item
          span.is-bold.is-link {{repo.language}}
        p.card-footer-item
          span
            | View on 
            a(:href='repo.svn_url') Github
        
</template>

<script>
export default {
  name: 'Repos',
  props: {
    repo: Object
  },
  updated(){
    console.log(this.repo)
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="sass">

</style>