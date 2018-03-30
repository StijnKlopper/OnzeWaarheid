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
      <router-view/>
    </v-app>
  </div>
</template>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  background-image: url("https://img.thedailybeast.com/image/upload/v1492176503/articles/2015/09/30/lawsuit-your-candy-bar-was-made-by-child-slaves/150929-haglage-chocolate-tease_ojn06f.jpg");
}

</style>
