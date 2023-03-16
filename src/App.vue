<script setup>
import { def } from '@vue/shared';
import product from './components/product.vue';

</script>

<template>
  <div >
    <div class=" bg-primary p-4 z-9  rounded-3 mb-2">
      <label for="" class="form-label">Total: <h1>{{ total }} </h1> 

    </label>
    </div>

  
    <div class="container" v-for="item in productNames" :key="item.id">
      <product @update = "upDate" :product-name="item.itemName" :value="item.value" :id = "item.id"></product>
    </div>
    
  
    
  </div>

</template>

<script>
export default {
  data() {
    return {
      productNames: [
        { id:1, itemName: "Love", value:1000, subTotal: 0 },
        { id:2, itemName: "Ego", value:500, subTotal: 0 },
        { id:3, itemName: "Hate", value:2000, subTotal: 0 },
        { id:4, itemName: "Humenrity", value:5000, subTotal: 0}
      ],
      total:0
    }
  },
  methods:{
    upDate(subTotal){
      this.total = 0
      this.productNames[subTotal[0]-1].subTotal = subTotal[1]
      this.productNames.forEach(
        (obj)=>{
          this.total += obj.subTotal
        }
      )
      
    }
  }
}
</script>

<style scoped></style>
