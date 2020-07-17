<template>
  <div>
    <div class="row">
      <div class="col-sm-12">
        <div class="card my-3">
          <div class="card-body">
            <h5 class="card-title">Name:{{ name }}</h5>
            <p class="card-text">Email: {{ email }}</p>
            <router-link :to="'/users/' + id" class="btn btn-primary"
              >Click</router-link
            >
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "User",
  props: ["id", "name", "email"],
};
</script>

<style>
.card {
  box-shadow: 0px 0px 5px #8888;
}
</style>
