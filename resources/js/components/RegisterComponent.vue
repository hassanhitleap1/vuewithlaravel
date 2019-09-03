
<template>
  <div>
    <h1>Register</h1>
    <form @submit.prevent="registerMethod">
      <div class="row">
        <div class="col-md-6">
          <div class="form-group">
            <label>Username:</label>
            <input type="text" class="form-control" v-model="register.username">
          </div>
        </div>
        </div>
        <div class="row">
        <div class="col-md-6">
          <div class="form-group">
            <label>email:</label>
            <input type="text" class="form-control" v-model="register.email">
          </div>
        </div>
        </div>

      
            <div class="row">
        <div class="col-md-6">
          <div class="form-group">
            <label>password:</label>
            <input type="password" class="form-control" v-model="register.password">
          </div>
        </div>
        </div>
  <div class="row">
        <div class="col-md-6">
          <div class="form-group">
            <label>confPassword:</label>
            <input type="password" class="form-control" v-model="register.confPassword">
          </div>
        </div>
        </div>

        
       
        <br />
        <div class="form-group">
          <button class="btn btn-primary">register</button>
        </div>
    </form>
  </div>
</template>

<script>
import {Validation} from '../core_class/validation';

    export default {
        data(){
        return {
         errors: [],
          register:{
              username:null,
              email:null,
              password:null,
              confPassword:null,
          }
        }
    },
    methods: {
      registerMethod(){
         var validation = new Validation();
         validation.isRequaied(this.username);
        return;
        let uri = 'http://localhost:8000/api/login';
        this.axios.post(uri, this.register).then((response) => {
            
          //this.$router.push({name: 'posts'});
        });
      }
    }
  }
</script>