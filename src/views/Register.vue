<template>
  <v-container pt-5>
    <v-layout
      row
      wrap
      justify-center>
      <v-flex
        xs12
        sm6>
        <v-card>
          <v-toolbar
            dark
            color="primary">
            <v-toolbar-title>
              Register
            </v-toolbar-title>
          </v-toolbar>
          <v-container
            style="border-left: solid grey 1px; border-right: solid grey 1px; border-bottom: solid grey 1px"
            fluid>
            <v-layout
              row
              wrap
              justify-center>
              <v-flex xs11>
                <v-form
                  v-model="valid"
                  ref="form"
                  lazy-validation>
                  <v-text-field
                    label="Username"
                    hint="At least 5 characters long"
                    type="text"
                    autofocus
                    clearable
                    required
                    v-model="username"
                    :rules="usernameRules"/>
                  <v-text-field
                    label="Email"
                    type="email"
                    clearable
                    required
                    v-model="email"
                    :rules="emailRules"/>
                  <v-text-field
                    label="Password"
                    hint="At least 8 characters long"
                    type="password"
                    clearable
                    required
                    v-model="password"
                    :rules="passwordRules"/>
                  <v-text-field
                    label="Confirm Password"
                    type="password"
                    clearable
                    required
                    v-model="cpassword"
                    :rules="cpasswordRules"/>
                </v-form>
                <v-btn
                  color="primary"
                  @click="submit">
                  Submit
                </v-btn>
              </v-flex>
            </v-layout>
          </v-container>
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  data () {
    return {
      success: false,
      username: '',
      usernameRules: [
        v => !!v || 'Name is required',
        v => (v && v.length >= 5) || 'Name must be at least 5 characters long'
      ],
      email: '',
      emailRules: [
        v => !!v || 'E-mail is required',
        v => /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/.test(v) || 'E-mail must be valid'
      ],
      password: '',
      passwordRules: [
        v => !!v || 'Password is required',
        v => (v && v.length >= 8) || 'Password must be at least 8 characters long'
      ],
      cpassword: '',
      cpasswordRules: [
        v => !!v || 'Password confirmation is required',
        v => (v && v === this.password) || 'Passwords do not match'
      ]
    }
  },
  methods: {
    submit () {
      if (!this.$refs.form.validate()) {
        this.success = false
        return
      }
      this.success = true
    }
  }
}
</script>

<style>

</style>
