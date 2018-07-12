<template>
  <div class="container">
    <div class="row">
      <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
        <h1>Http</h1>
        <div class="form-group">
          <label>Username</label>
          <input class="form-control" type="text" v-model="user.Username">
        </div>
        <div class="form-group">
          <label>Email</label>
          <input class="form-control" type="text" v-model="user.email">
        </div>
        <button class="btn btn-primary" @click="submit">Submit</button>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        user: {
          Username: '',
          email: ''
        }
      };
    },
    methods: {
      submit() {
        this.$http.post('https://vuejs-http-7d3b3.firebaseio.com/project.json', this.user)
          .then(response => {
            console.log(response)
          }, error => {
            console.log(error);
          });
      }
    }
  }
</script>

<style>

</style>
