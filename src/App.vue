<template>
  <div id="app">
    <v-app>
      <v-toolbar
        dark
        color="primary">
        <v-toolbar-side-icon/>
        <v-toolbar-title>
          <router-link
            to="/"
            tag="span"
            style="cursor: pointer">
            App
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
}
</style>
