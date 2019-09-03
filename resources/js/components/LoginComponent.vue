
<template>
  <div>
    <h1>login</h1>
    <form @submit.prevent="loginMethod">
      <div class="row">
        <div class="col-md-6">
          <div class="form-group">
            <label>Username:</label>
            <input type="text" class="form-control" v-model="login.username">
          </div>
        </div>
        </div>

        <div class="row">
        <div class="col-md-6">
          <div class="form-group">
            <label>password:</label>
            <input type="password" class="form-control" v-model="login.password">
          </div>
        </div>
        </div>
       
        <br />
        <div class="form-group">
          <button class="btn btn-primary">Login</button>
        </div>
    </form>
  </div>
</template>

<script>
    export default {
        data(){
        return {
          login:{}
        }
    },
    methods: {
      loginMethod(){
        let uri = 'http://localhost:8000/api/login';
        this.axios.post(uri, this.post).then((response) => {
            
          //this.$router.push({name: 'posts'});
        });
      }
    }
  }
</script>