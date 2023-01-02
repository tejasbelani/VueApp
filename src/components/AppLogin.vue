<template>

<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@4.3.1/dist/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">

    
   

    <center>

        <div v-if="this.showdvLoginform">

                    <form>

        <div style="text-align:center">
        <h1> App Login </h1>
        </div>

        <!-- Email input -->
        <div class="form-outline mb-4 col-md-3">
        <input type="email" id="form2Example1" placeholder="Email address" v-model="username" class="form-control" />
        </div>

        <!-- Password input -->
        <div class="form-outline mb-4 col-md-3">
        <input type="password" id="form2Example2" placeholder="Password" v-model="password" class="form-control" />
        </div>

        <!-- 2 column grid layout for inline styling -->


        <!-- Submit button -->
        <button type="button" @click="login()" class="btn btn-primary btn-block col-md-3 mb-4">Sign in</button>


                </form>
        </div>
       
       



        <div v-if="this.islogged">

             

             
             <Hello  msg="Hello, Tejas Belani Here"> </Hello>

            <hr /> 

             <AlphabetMsg alphabetmsg="a,b,c,d,e,f,g,h,i,j,k,l,m,n,o,p,q,r,s,t,u,v,w,x,y,z"> </AlphabetMsg>

            <hr/>

            <RectangleVue> </RectangleVue>
             <br /> 
            <hr/>


        </div>

        <p v-if="this.isInValid">
             In valid user.
        </p> 

    </center>

  </template>



<script>

import Hello from './Hello.vue';
import AlphabetMsg from './AlphabetMsg.vue';
import RectangleVue from './Rectangle.vue';

export default {
  name: "AppLogin",
  components:{
    Hello,
    AlphabetMsg,
    RectangleVue   
  },
  data() {
        return {
            islogged: false,
            isInValid: false,
            showdvLoginform: true
        }
      },
  methods: {
    login()
    {
      if(this.username == 'admin' && this.password == 'admin')
      {
        this.islogged = true;
        this.isInValid = false;
        this.showdvLoginform = false;
      }
      else {
        this.isInValid = true;
      }
           
    }
  },
};
</script>