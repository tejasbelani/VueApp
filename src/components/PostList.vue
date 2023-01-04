<script>

export default{
    props:
    {
        data:[]
    },
    data() {
        return {
            postlist:[
                { name: 'Ring Ceremony',description: 'This is test event1',date: '03-01-2023',image: '' }, 
                { name: 'Government Event',description: 'This is test event2',date: '03-01-2023',image: '' },
                { name: 'Public Event',description: 'This is test event3',date: '03-01-2023',image: '' },
                { name: 'Carnival Event',description: 'This is test event4',date: '03-01-2023',image: '' },
                { name: 'Global Event',description: 'This is test event5',date: '03-01-2023',image: '' },
                { name: 'Private Events',description: 'This is test event6',date: '03-01-2023',image: '' }
            ],
            splist:[],
            showpostdv: false
        }
    },
    methods:{
        addtofavouritepost(p)
        {
            this.splist.push(p);
           // this.$emit("notify",this.splist,"Abc");
        },
        showlikedevent()
        {
            this.showpostdv = true;
        },
    }
}
</script>


<template>

<table border="1px">
    <tr>
        <th>Post Name</th>
        <th>Post Description</th>
        <th>Posted Date</th>
        <th>Posted Image</th>
        <th>Action</th>
    </tr>
    <tr v-if="this.postlist.length <= 0">
        <td colspan="5">No data available</td>
    </tr>
    <tr v-for="p in postlist">
      <td> {{p.name}}</td>
      <td>{{p.description}}</td>
      <td>{{p.date}}</td>
      <td>{{p.image}}</td>
      <td> <button @click="addtofavouritepost(p)" class="btn btn-primary">Like</button> </td>
    </tr>
  </table>

  <br/>

  <h1>Favourite Post List</h1>
  Number of Likes:  {{ splist.length }} <button class="btn btn-primary" @click="showlikedevent()">Show Details</button>

  <table border="1px" v-if="this.showpostdv">
    <tr>
        <th>Post Name</th>
        <th>Post Description</th>
        <th>Posted Date</th>
        <th>Posted Image</th>
        <th></th>
    </tr>
    <tr v-if="this.splist.length <= 0">
        <td colspan="5">No data available</td>
    </tr>
    <tr v-for="likpost in splist">
      <td> {{likpost.name}}</td>
      <td>{{likpost.description}}</td>
      <td>{{likpost.date}}</td>
      <td>{{likpost.image}}</td>
      <td> Liked </td>
    </tr>
  </table>

</template>
