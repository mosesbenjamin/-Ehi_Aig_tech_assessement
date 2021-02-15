<template>
  <div id="app">
   <Header v-bind:user="user"/>
   <Profile v-bind:user="user" v-bind:starred="starred" v-bind:repos="repos" v-bind:orgs="orgs" />
   <Footer />
  </div>
</template>

<script>
import axios from 'axios';

import Header from './components/layout/Header.vue';
import Footer from './components/layout/Footer.vue';
import Profile from './components/Profile.vue';

export default {
  name: 'App',
  components: {
    Header,
    Footer,
    Profile
  },
  data() {
    return {
      user: [],
      starred: [],
      repos: [],
      orgs: []
    }
  },
  async created() {

    const baseURL = 'https://api.github.com/users'
    const user = 'mosesbenjamin'
    try {
      const {data} = await axios.get(`${baseURL}/${user}`)
      this.user = data    
    } catch (error) {
      console.error(error)
    }

    try {
      const {data} = await axios.get(`${baseURL}/${user}/starred`)
      this.starred = data
    } catch (error) {
      console.error(error)
    }

    try {
      const {data} = await axios.get(`${baseURL}/${user}/repos`)
      this.repos = data
    } catch (error) {
      console.error(error)
    }

    try {
      const {data} = await axios.get(`${baseURL}/${user}/orgs`)
      this.orgs = data
    } catch (error) {
      console.error(error)
    }
  }
}
</script>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300&display=swap');
  
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  button {
    cursor: pointer;
    transition: all 100ms ease-in-out ;
  }

  button:active, a:active {
    transform: scaleY(0.95);
  }
  a {
    text-decoration: none;
  }
</style>
