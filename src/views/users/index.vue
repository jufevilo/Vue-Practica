<template>
  <div id="app">
    <img alt="Vue logo" src="../../assets/logo.png" />
    <div class="row">
      <div class="col-sm-12">
        <User
          v-for="user of users"
          :key="user.id"
          :name="user.name"
          :email="user.email"
          :id="user.id"
        />
      </div>
    </div>
  </div>
</template>
<script>
// Declarar la librería
import axios from "axios";
import Vue from "vue";
import User from "../../components/User";
Vue.use(User);

export default {
  components: {
    User: User
  },
  data() {
    return {
      users: []
    };
  },
  // Evento
  mounted() {
    axios
      .get("https://jsonplaceholder.typicode.com/users")
      .then(response => {
        this.users = response.data;
        console.log(this.users);
      })
      .catch(e => {
        console.log(e.response);
      });
  }
};
</script>
<style>
.row {
  text-align: left !important;
}
</style>
