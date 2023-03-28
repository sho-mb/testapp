<template>
  <v-form>
    <v-container class="mt-16 grey lighten-3">
      <h1 class="text-center my-8">Login</h1>
      <v-row justify="space-around" align="center" class="pa-8">
        <v-col md="5">
          <v-text-field
          v-model="email"
         :rules="emailRules"
          label="E-mail"
          required
          ></v-text-field>
          <v-text-field
            v-model="password"
            :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
            :rules="[rules.required, rules.min]"
            :type="show1 ? 'text' : 'password'"
            name="password"
            label="Password"
            hint="At least 8 characters"
            counter
            @click:append="show1 = !show1"
          ></v-text-field>
          <a>Forget password?</a>

          <h3>Security Check</h3>
          <p>Please enter the word in input from picture</p>
          <v-img></v-img>
          <v-text-field
          v-model="security"
          label="Texy from pictire"
          name="security"
          ></v-text-field>
          <v-btn
          color="primary"
          rounded
          x-large
          > <div class="mx-8">Login</div>
          </v-btn>
        </v-col>
        <v-divider vertical></v-divider>
        <v-col md="5">
          <v-btn
          outlined
          rounded
          x-large
          class="mb-8 pa-7 white"
          >
          <v-icon left color="red" >
            mdi mdi-google
          </v-icon>
          <div class="ma-10">Login with google account</div>
          </v-btn>
          <v-btn
          outlined
          rounded
          x-large
          class="mb-8 pa-7 white"
          >
          <v-icon left color="blue" >
            mdi mdi-facebook
          </v-icon>
          <div class="ma-10">Login with google account</div>
          </v-btn>
          <v-btn
          outlined
          rounded
          x-large
          class="pa-7 white"
          >
          <v-icon left >
            mdi mdi-apple
          </v-icon>
          <div class="ma-10">Login with google account</div>
          </v-btn>
        </v-col>
      </v-row>
    </v-container>
  </v-form>
</template>
<script>
export default {
  data () {
      return {
        valid: true,
      email: '',
      emailRules: [
        v => !!v || 'E-mail is required',
        v => /.+@.+\..+/.test(v) || 'E-mail must be valid',
      ],
        show1: false,
        password: 'Password',
        rules: {
          required: value => !!value || 'Required.',
          min: v => v.length >= 8 || 'Min 8 characters',
          emailMatch: () => (`The email and password you entered don't match`),
        },
      }
    },

    methods: {
      validate () {
        this.$refs.form.validate()
      },
      reset () {
        this.$refs.form.reset()
      },
      resetValidation () {
        this.$refs.form.resetValidation()
      },
    },
  }
</script>
