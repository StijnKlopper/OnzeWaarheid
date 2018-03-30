<template>
  <div id="app">
    <v-app>
      <v-toolbar
        dark
        color="light-green darken-1">
        <v-toolbar-side-icon/>
        <v-toolbar-title>
          <router-link
            to="/"
            tag="span"
            style="cursor: pointer">
            Onze Waarheid
          </router-link>
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
      <transition name="fade">
        <router-view/>
      </transition>
      <transition name="stay">
        <Footer/>
      </transition>
    </v-app>
  </div>
</template>

<script>
import Footer from '@/components/Footer.vue'

export default {
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
  background-image: url("https://img.thedailybeast.com/image/upload/v1492176503/articles/2015/09/30/lawsuit-your-candy-bar-was-made-by-child-slaves/150929-haglage-chocolate-tease_ojn06f.jpg");
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
.stay-enter-active, .stay-leave-active {
  transition-property: opacity;
  transition-duration: 0s;
}

.stay-enter-active {
  transition-delay: 0s;
}

.stay-enter, .stay-leave-active {
  opacity: 0
}
</style>
