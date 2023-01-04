<script>

export default{
    props:
    {
        message:String,
        data:[]
    },
    data() {
        return {
            productDisplaylist:[]
        }
    }
}
</script>


<template>

<table border="1px">
    <tr>
        <th>Product Name</th>
        <th>Product Price</th>
        <th>Product Quantity</th>
        <th>Product Discount</th>
    </tr>
    <tr v-if="this.data.length <= 0">
        <td colspan="4">No data available</td>
    </tr>
    <tr v-for="p in data">
      <td> {{p.name}}</td>
      <td>{{p.price}}</td>
      <td>{{p.quantity}}</td>
      <td>{{p.discount}}</td>
    </tr>
  </table>

</template>
