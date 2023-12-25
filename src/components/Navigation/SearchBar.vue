<template>
    <input type="text" placeholder="Search" class="search">
    <span :class="name"><Icon :link="Search"/></span>
</template>
<script>
import Search from '../../Assets/search.svg';
import Icon from '../Content/icons.vue';

export default {
    data(){
        return{
            Search
        }
    },
    components:{
        Icon
    },
    props:{
        name:{
            type:String,
            required:true
        }
    }
}
</script>
<style scoped>
.search{
    border: 1px solid #d9e1cc;
    padding: 10px 20px;
    border-radius: 20px;
    outline: none;
}
.img{
    position: absolute;
    right: 11px;
    top: 9px;
}
.asset{
    position: relative;
    top: 5px;
    right: 25px;
}

</style>