<template>

    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@4.3.1/dist/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
    
    <center style="margin-top:50px;">
           
    <form>

    <div v-show="this.usersignup">
    
    <div style="text-align:center">
      <h1> App SignUP </h1>
    </div>
    
    <!-- Email input -->
    <div class="form-outline mb-4 col-md-3">
    <input type="text" id="form2Example1" placeholder="First Name" maxlength="20" v-model="firstname" class="form-control" />
    </div>
    
    <!-- Password input -->
    <div class="form-outline mb-4 col-md-3">
    <input type="text" id="form2Example2" placeholder="Last Name" maxlength="20" v-model="lastname" class="form-control" />
    </div>
    
    <div class="form-outline mb-4 col-md-3">
    <input type="text" rows="4" cols="10" id="form2Example2" maxlength="50" placeholder="Address" v-model="address" class="form-control" />
    </div>
    
    <div class="form-outline mb-4 col-md-3">
    <input type="text" id="form2Example2" placeholder="PAN Number" maxlength="10" v-model="pannumber" class="form-control" />
    </div>
    
    <!-- Submit button -->
    <button type="button" @click="signup()" class="btn btn-primary btn-block col-md-3 mb-4">Sign UP</button>

    <p v-if="this.isInValid">
             Please enter valid data.
        </p> 

    </div>
    
    <div>
        <AppLoginVue v-if="this.userlogin"> </AppLoginVue>
    </div>

    </form>
    
    </center>
    
        
    
    
</template>
    
    
    
    
    <script>

    import AppLoginVue from './AppLogin.vue';

    export default {
      name: "AppSignUp",
      components:{
        AppLoginVue
      },
      data() {
        return {
        userlogin: false,
        usersignup: true,
        isInValid: false,
        }
      },
      methods: {
        signup()
        {
            
          if(this.firstname == undefined || this.lastname == undefined || this.address == undefined || this.pannumber == undefined)
          {
            this.userlogin = false;
            this.usersignup = true;
            this.isInValid = true;
          }
          else if(this.firstname != '' && this.lastname != '' && this.address != '' && this.pannumber != '')
          {
            this.userlogin = true;
            this.usersignup = false;
          }
               
        }
      },
    };
    </script>