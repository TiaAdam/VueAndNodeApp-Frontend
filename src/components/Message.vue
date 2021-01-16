<template>
  <v-flex sm8 offset-sm2>
    <v-card>
      <v-toolbar dark>
        <v-toolbar-title> Message </v-toolbar-title>
      </v-toolbar>
      <v-card-text>
      {{message.text}}
      </v-card-text>
    </v-card>
  </v-flex>
</template>

<script>
import axios from "axios";
//import store from "../store.js";

export default {
  data() {
    return {
      message: "",
    };
  },
 async  created() {
    this.message = ( await this.$store.dispatch("getMessage", this.$route.params.id));
  },
  //async created() {
  //this.messages = (await axios.get('http://localhost:3000/messages')).data;
  //},

};
</script>
