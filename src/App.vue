<template>
  <div id="app">
    <v-app>
      <v-navigation-drawer
        id="drawerid"
        fixed
        clipped
        app
        v-model="drawer"/>
      <v-toolbar
        style=""
        id="toolbar"
        app
        clipped-left
        light
        color="white">
        <v-btn
          flat
          fab
          @click="drawer = !drawer">
          <v-icon x-large="">menu</v-icon>
        </v-btn>
        <v-toolbar-title>
          <router-link
            to="/"
            tag="span"
            style="cursor: pointer"/>
        </v-toolbar-title>
        <v-spacer/>
        <v-toolbar-items>
          <v-btn
            flat
            to="/register">
            Register
          </v-btn>
          <v-btn
            flat
            to="/login">
            Login
          </v-btn>
        </v-toolbar-items>
      </v-toolbar>
      <v-progress-linear value="50"/>
      <v-content>
        <v-container>
          <transition name="fade">
            <router-view/>
          </transition>
        </v-container>
      </v-content>
      <Footer id="footer"/>
    </v-app>
  </div>
</template>

<script>
import Footer from '@/components/Footer.vue'

export default {
  data () {
    return {
      drawer: false
    }
  },
  components: {
    Footer
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
.fade-enter-active, .fade-leave-active {
  transition-property: opacity;
  transition-duration: .25s;
}

.fade-enter-active {
  transition-delay: .25s;
}

.fade-enter, .fade-leave-active {
  opacity: 0
}
</style>
