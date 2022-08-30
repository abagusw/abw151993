<script>
export default {
  data: () => ({
    valid: false,
    username: "",
    show1: false,
    password: "",
    rules: {
      required: (value) => !!value || "Required.",
      min: (v) => v.length >= 8 || "Min 8 characters",
      emailMatch: () => `The email and password you entered don't match`,
    },
  }),
  methods: {
    submit: async function () {
      const axios = require('axios');
      const self = this;
      axios({
        method: "post",
        url: "36.66.184.26:8002/api/bjtg/rekruitmen/login",
        auth: {
          username: self.username,
          password: self.password,
        },
      }).then(function (response) {
        console.log(response)
      });
    },
  },
};
</script>

<template>
  <v-container>
    <v-card>
      <v-form v-model="valid">
        <v-row>
          <v-col>
            <v-text-field
              v-model="username"
              label="Username"
              required
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row>
          <v-col>
            <v-text-field
              v-model="password"
              :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
              :rules="[rules.required, rules.min]"
              :type="show1 ? 'text' : 'password'"
              name="input-10-1"
              label="Normal with hint text"
              hint="At least 8 characters"
              counter
              @click:append="show1 = !show1"
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row class="mb-2">
          <v-col>
            <v-btn @click="submit" color="success" class="d-flex justify-right"> Continue </v-btn>
          </v-col>
        </v-row>
      </v-form>
    </v-card>
  </v-container>
</template>
