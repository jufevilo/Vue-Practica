<template>
  <div>
    <h1>User Details</h1>
    <div class="row">
      <div class="col-sm-12">
        <div class="card mt-5">
          <div class="card-body">
            <h5 class="card-title"><strong>Name:</strong> {{ user.name }}</h5>
            <p class="card-text"><strong>Email:</strong> {{ user.email }}</p>
            <p class="card-text">
              <strong>Address:</strong><br />
              Ciudad:{{ user.address.city }}<br />
              Calle:{{ user.address.street }}<br />
              Apt:{{ user.address.suite }}<br />
              Zip Code:{{ user.address.zipcode }}
            </p>
            <p class="card-text"><strong>Phone:</strong> {{ user.phone }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      user: [],
    };
  },
  // Evento
  created() {
    axios
      .get(
        "https://jsonplaceholder.typicode.com/users/" + this.$route.params.id
      )
      .then((response) => {
        this.user = response.data;
        console.log(this.user);
      });
  },
};
</script>

<style></style>
