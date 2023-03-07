<template>
    <div>
        <label for="">{{ productName }}</label>
    </div>
</template>

<script>
    export default {
        data(){
            return{
                productName:""
            }
        },
        props:['productName']
    }
</script>

<style lang="scss" scoped>

</style>