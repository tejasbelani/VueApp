<script>

import Hello from './components/Hello.vue';
import AlphabetMsg from './components/AlphabetMsg.vue';
import RectangleVue from './components/Rectangle.vue';


const routes = {
  '/': Hello,
  '/alpha': AlphabetMsg,
  '/rectangle': RectangleVue
}

export default {
  data() {
    return {
      currentPath: window.location.hash
    }
  },
  computed: {
    currentView() {
      return routes[this.currentPath.slice(1) || '/'] || NotFound
    }
  },
  mounted() {
    window.addEventListener('hashchange', () => {
		  this.currentPath = window.location.hash
		})
  }
}
</script>

<template>
  <a href="#/">Home</a> |
  <a href="#/about">About</a> |
  <a href="#/non-existent-path">Broken Link</a>
  <component :is="currentView" />

  

</template>