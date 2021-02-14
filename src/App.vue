<template>
  <div id="app">
   <Header />
   <Profile v-bind:user="user" v-bind:starred="starred" v-bind:orgs="orgs"/>
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
      starred: []
    }
  },
  async created() {
    try {
        const {data} = await axios.get('https://api.github.com/users/mosesbenjamin')
        this.user = data    
    } catch (error) {
        console.error(error)
    }

    try {
      const {data} = await axios.get('https://api.github.com/users/mosesbenjamin/starred')
      this.starred = data
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
  }
</style>
