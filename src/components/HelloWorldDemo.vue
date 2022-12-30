<script>
export default{
    props:{message:String,data:[]},
    data() {
        return {
            splist:[]
        }
    },
    methods:{
        sponsorslist(p)
        {
            this.splist.push(p);
            this.$emit("notify",this.splist,"Abc");
        }
    }
}
</script>
<template>
<h1>{{message}}</h1>

<table>
    <tr v-for="p in data">
      <td>{{p.name}}</td>
      <td>{{p.address}}</td>
      <td>{{p.status}}</td>
        <td><button @click="sponsorslist(p)">Give sponser</button></td>
    </tr>
  </table>
</template>
<style>
</style>