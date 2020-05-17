<template lang="pug">
  .home
    div(v-for="item in reps_show")
      .container
        Repos(:repo="item")
    div(v-if="end").p-y-2
      .is-small end of list
</template>

<script>
import Repos from 'src/components/Repos'
import axios from 'axios'

export default {
  name: 'home',
  components: {
    Repos
  },
  data() {
    return {
      reps:[],
      reps_show:[],
      end:false
    }
  },
  beforeMount(){
    axios('https://api.github.com/users/mutsuki333/repos')
    .then(res=>{this.reps=res.data;this.append_reps();console.log(this.reps[0])})
  },
  methods:{
    append_reps(){
      if(this.end)return
      console.log(this.reps_show.length)
      let l=this.reps_show.length
      for (let i = l; i < l+5; i++) {
        if(i>this.reps.length){
          this.end=true
          return
        }
        this.reps_show.push(this.reps[i])
      }
      
    }
  },
  created(){
    let that = this;
    window.onscroll = function(ev) {
      console.log("scroll")
      if ((window.innerHeight + window.pageYOffset) >= document.body.offsetHeight) {
        if(that.end)return
        that.append_reps()
      }
    };
  }
}
</script>
