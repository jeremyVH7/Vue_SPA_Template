<template>
  <div>
    <div id="app">
      <div class='row' id='title-h1-div'><h1 id='title-h1'>{{ title }}</h1></div>
      <NavBar>
        <ul>
          <li><router-link to="/"><img id="vue-logo" src="./assets/logo.png"></router-link></li>
          <li v-for='(link, i) in buttonLinks' :key='i'><NavButton v-bind:routerTo="link[0]" v-bind:buttonText="link[1]"></NavButton></li>
        </ul>
      </NavBar>
      <router-view/>

    </div>
  </div>
</template>

<script>
import {EventBus} from './components/EventBus.js'
import NavBar from './components/NavBar.vue'
import NavButton from './components/NavButton.vue'
import NavDropdown from './components/NavDropdown.vue'
import NavSearch from './components/NavSearch.vue'
import Home from './components/Home.vue'
import About from './components/About.vue'
import Error404 from './components/Error404.vue'

export default {
  name: 'app',
  components: {
    NavBar: NavBar,
    NavButton: NavButton,
    Home: Home,
    About: About,
    Error404: Error404
  },
  data () {
    return {
      title: 'Vue Single Page Template',
      buttonLinks: [
        ['/home', 'Home'],
        ['/about', 'About']

        // ['/error404', 'Error']
      ]
    }
  },
  methods: {

  },
  created: function () {
    // EventBus.$on('button-clicked', this.buttonClicked);
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: white;
}

h1, h2 {
  font-weight: normal;
  padding-left: 40px;
  position: relative;
}

body {
  background: grey;
}

ul {
  list-style-type: none;
}

li {
  display: inline-block;
  padding-right: 5px;
}
.d-btn {
  background: blue;
  /* height: 100px;
  width: 100%; */
  cursor: pointer;
}
#nav-demo {
  position: relative;
}
</style>
