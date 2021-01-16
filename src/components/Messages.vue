<template>
  <v-flex sm8 offset-sm2>
    <v-card>
      <v-toolbar dark>
        <v-toolbar-title> Messages </v-toolbar-title>
      </v-toolbar>
      <v-list>
        <v-list-tile
          v-for="(message, index) in $store.state.messages"
          :key="message.messages"
          :to="'message/' + index"
        >
          <v-list-tile-content>
            <v-list-tile-title v-text="message.text"></v-list-tile-title>
             <v-list-tile-sub-title v-text="message.user"></v-list-tile-sub-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-card>
  </v-flex>
</template>

<script>
//import axios from "axios";
//import store from "../store.js";

export default {
  async created() {
    //let messages = (await axios.get("http://localhost:3000/messages")).data;
    this.$store.dispatch("getMessages");
  },
};
</script>
