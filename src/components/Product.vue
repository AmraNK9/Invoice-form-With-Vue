<template>
    <div >
        <div>
            <label class="form-label"  for="">
                <h1>{{ productName }}</h1>
            </label>
        </div>

        <div>
            <label class="form-label" for="">Quitity</label>
            <input class="form-control"  type="number" v-model="Quitity">
        </div> 

        <div>
            <label class="form-label" for="Price">Price</label>
            <input class="form-control" type="text" :value="value" aria-label="Disabled input example" disabled>
        </div>
         <div>
            <label for="form-label" class="form-label" >Sub Total</label>
            <label for="" class="form-label">
                <h2>{{ subTotal }}</h2>
            </label>
         </div>
    </div>
    

    
    
  
</template>
    
<script>
    import "bootstrap/dist/css/bootstrap.min.css"
    export default {
        data(){
            return{
              Quitity:0,
              subTotal:0,
                
            }
        },
        props:['productName',"value","id"],
        watch:{
            Quitity(qty){
                this.subTotal = qty * this.value
                this.$emit("update",[this.id,this.subTotal])
            }
        }
    }
</script>

<style  scoped>

div{
    margin-bottom: 5px;
}
.container{
    margin: 20px;
}
</style>