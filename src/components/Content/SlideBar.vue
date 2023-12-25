<template>
    <ul class="listContainer">
        <li v-for="(item,index) in images" :key="index"><img :src="item" alt=""></li>
    </ul>    
</template>
<script>
export default {
    data(){
        return{
            
        }
    },
    props:{
        images:{
            type:Object,
            required:true
        }
    }
}
</script>
<style scoped>
.listContainer{
    display: flex;
    gap: 30px;
    list-style: none;
}
ul li:nth-child(1)::after{
    content: '38';
    font-size: 10px;
    font-weight: bold;
    color: white;
    background: pink;
    padding: 1px 4px;
    border-radius: 8px;
    position: absolute;
    top: -7px;
    left: 10px;
}
ul li:nth-child(2)::after{
    content: '12';
    font-size: 10px;
    font-weight: bold;
    color: white;
    background: yellow;
    padding: 1px 4px;
    border-radius: 8px;
    position: absolute;
    top: -9px;
    left: 54px;
}
ul li:nth-child(3)::after{
    content: '!';
    font-size: 10px;
    font-weight: bold;
    color: white;
    background: rgb(170, 12, 12);
    padding: 1px 6px;
    border-radius: 6px;
    position: absolute;
    top: -9px;
    right: 80px;
    
}
ul li:nth-child(4)::after{
    content: '67';
    font-size: 10px;
    font-weight: bold;
    color: white;
    background: green;
    padding: 1px 3px;
    border-radius: 6px;
    position: absolute;
    top: -9px;
    right: 35px;
    
}


</style>