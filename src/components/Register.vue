<template>
  <v-flex sm8 offset-sm2>
    <v-card>
      <v-toolbar dark>
        <v-toolbar-title> Register </v-toolbar-title>
      </v-toolbar>
      <v-form>
        <v-container>
          <v-row>
            <v-col cols="12" md="4">
              <v-text-field
                v-model="userName"
                label="User Name"
                required
              ></v-text-field>
            </v-col>
            <v-col cols="12" md="4">
              <v-text-field
                v-model="password"
                label="Password"
                required
              ></v-text-field>
            </v-col>
          </v-row>
        </v-container>
        <v-btn class="mr-4" @click="register">
          Register
        </v-btn>
      </v-form>
    </v-card>
  </v-flex>
</template>

<script>
import axios from "axios";
//import store from "../store.js";

export default {
  data() {
    return {
      userName: "",
      password: "",
    };
  },
  //async created() {
  //this.messages = (await axios.get('http://localhost:3000/messages')).data;
  //},
  methods: {
    async register() {
      this.$store.dispatch("register", {userName: this.userName, password: this.password});
    },
  },
};
</script>
