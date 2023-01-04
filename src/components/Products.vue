<template>

<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@4.3.1/dist/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">



    <div class="row">

        <div class="col-md-6">

            <center>
            
            <h1> Product Details </h1>

            <div class="form-outline mb-4">
             <input type="text" v-model="product.name" placeholder="Product Name" class="form-control  col-md-4" />
            </div>
            <div class="form-outline mb-4">
                <input type="number" v-model="product.price" placeholder="Price" class="form-control col-md-4" />
            </div>
            <div class="form-outline mb-4">
                <input type="number" v-model="product.quantity" placeholder="Quantity " class="form-control col-md-4" />
            </div>
            <div class="form-outline mb-4">
                <input type="number" v-model="product.discount" placeholder="Discount" class="form-control col-md-4" />
            </div>

            <button @click="addproducts()" class="btn btn-primary btn-block col-md-4 mb-4">Add product</button> 

            <p v-if="this.isInValid">
               Please enter valid data.
            </p> 

            <h1> Product List </h1>
            <ProductListVue @notify="producInfo($event)" :data="productlist">  </ProductListVue>
            
        </center>
        
        </div>
        
        
        <div class="col-md-6">
           
            <br/>
            <h1> Post List </h1>
            <PostListVue></PostListVue>
        </div>
        

    </div>

    
   
    
   



    
</template>


<script>

import ProductListVue from './ProductList.vue';
import PostListVue from './PostList.vue';

  export default {
    name: "Products",
    components:{
        ProductListVue,
        PostListVue
    },
    data() {
    return {
        product:{},
        productlist:[],
        productDisplaylist:[],
        postlist:[],
        isInValid: false
    }
  },
  watch:{ 
    productlist:{
    handler(newValue,oldValue)
        {
          console.log("Value changed");
        },deep:'true'
  }},
  methods: {
    addproducts()
    {
      if(this.product.name == undefined || this.product.price == undefined || this.product.quantity == undefined || this.product.discount == undefined)
      {            
            this.isInValid = true;
      }
      else if(this.product.name != '' && this.product.price != '' && this.product.quantity != '' && this.product.discount != '')
      {
        this.product.price = "₹ " + this.product.price;
        this.productlist.push(this.product);
        this.product={};
      }

    
    },
    producInfo(data,abc)
    {
      this.productDisplaylist=data;
      console.log(abc)
    }  
  },
  };
  
  </script>