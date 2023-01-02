<template>
    <div>
      <h1> Rectangle Component</h1>
    </div>
    <div>
        Enter Length <input type="number" v-model="length" />
        Enter Width <input type="number" v-model="width" />
        <button @click="calculateArea()">Calculate Rectangle</button>
        
    </div>
  </template>

<script>
export default {
  name: "Rectangle",
  methods: {
    calculateArea()
    {
      let area = parseInt(this.width) * parseInt(this.length);
      alert("Rectangle Area is: "+area);      
    }
  },
};
</script>