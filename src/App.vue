<template>
  <div id="app">
    <Header />
    <Main 
    :myGit = 'myGit'
    :myGitRepo = 'myGitRepo'/>
    <Footer />
  </div>
</template>

<script>

import Header from './components/Header/Header.vue';
import Main from './components/Main/Main.vue';
import Footer from './components/Footer/Footer.vue';
import axios from 'axios';
import 'animate.css';

export default {
  name: 'App',
  components: {
    Header,
    Main,
    Footer,
  },
  data: function(){
    return{
      myGit: {},
      myGitRepo: []

    }
  },
  methods: {
    getMyGithub(){
      axios.get('https://api.github.com/users/AlexBosio95')
      .then((results) => {
        this.myGit = results.data
      })
    },
    getGitRepo(){
      axios.get('https://api.github.com/users/AlexBosio95/repos')
      .then((results) => {
        this.myGitRepo = results.data
      })

    }
  },
  created(){
    this.getMyGithub()
    this.getGitRepo()
  }

}
</script>

<style lang="scss">
@import '~bootstrap/scss/bootstrap.scss';
@import url('https://fonts.googleapis.com/css2?family=Roboto&display=swap');

body{
  background-color: #252734;
  font-family: 'Roboto', sans-serif;
  overflow-x: hidden;
}

</style>
