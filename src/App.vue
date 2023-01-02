<script>
import HelloWorldDemo from './components/HelloWorldDemo.vue';

import AppSignUpVue from './components/AppSignUp.vue';

import {reactive} from 'vue'
export default{
  setup()
  {
    const info=reactive({count:0})
    return{info}
  },
  components:{
    HelloWorldDemo,
    AppSignUpVue
  },
  data() {
    return {
      emp:{},
      users:[],
      info:45,
      theme:"lighttheme colorinfo",
      splist:[]
    }
  },
  computed:{
    CountInactive()
    {
     return this.users.filter(p=>p.status=="inactive").length;
    }  
  },
  watch:{ 
    users:{
    handler(newValue,oldValue)
        {
          console.log("Value changed");
        },deep:'true'
  }},
  methods: {
    demo()
    {
      this.users.push(this.emp);
      this.users[0].name="rahul";
      this.emp={};
    },
    info1(data,abc)
    {
      this.splist=data;
      console.log(abc)
    }
  },
}
</script>

<template>




  <AppSignUpVue></AppSignUpVue>

  

 




  <!-- Count{{ splist }} -->

 

  <!-- {{ info.count }} -->
<!-- <HelloWorldDemo @notify="info1($event)" message="Good Morning" :data="users"></HelloWorldDemo>

  <h1>Inactive USers{{CountInactive}}</h1>
  Enter Name <input type="text" v-model="emp.name"/>
  Enter Address <input type="text" v-model="emp.address"/>
Active  <input type="radio" value="active" v-model="emp.status"/>
InActive <input type="radio" value="inactive" v-model="emp.status"/>
<button @click="demo()">Add employee</button> -->

</template>

<style>
.lighttheme
{
  border:1px solid lightblue;
 
}
.colorinfo
{
  color:red;
  border:1px solid green;
 

}
</style>
