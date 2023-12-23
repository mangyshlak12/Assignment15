<template>
   <div class="container">
        <input type="range" min="1" max="100" v-model="value" class="range">
        <div class="minmax"><span>Min: 1</span>
        <span>Value: {{value}}</span>
        <span>Max: 100</span>
        </div>
   </div>
</template>
<script>
export default {
    data(){
        return{
            value: '1'
        }
    }
}
</script>
<style scoped>
.minmax{
    display: flex;
    justify-content: space-between;
}
.container{
    width: fit-content;
}
.range{
    width: 200px;
}
</style>