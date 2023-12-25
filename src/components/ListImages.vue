<template>
    <ul class="listContainer">
    <li :class="name" v-for="(item,index) in images" :key="index"><Icons :link="item" name="avatarrr" /></li>
    <li class="lastelement"  v-if="name === 'first' ">5+</li>
    </ul>
</template>
<script>
import Icons from './Content/icons.vue';


export default {
    data(){
        return{
           
        }
    },
    props:{
        images:{
            type: Object,
            required: true
        },
        name:{
            type: String,
            required: true
        }
    },
    components:{
        Icons
    },
    methods:{
        check(index){
            if(index!==1){
                return 8 * (index-1);
            }else{
                return 0;
            }
        }
    }
}
</script>
<style scoped>
ul{
    list-style: none;
    display: flex;
}
ul li{
    width: 29px;
    height: 29px;
    border: 2px solid #d9e1cc;
     border-radius: 50%;
}

.lastelement{
    display: flex;
    align-items: center;
   justify-content: center;
    color: white;
    font-weight: 700;
    background: rgba(123, 59, 196, 0.836);
    border-radius: 50%;
    position: relative;
    
    right: 32px;
}
ul li:nth-child(2){
 position: relative;
    right: 8px;
}
ul li:nth-child(3){
     position: relative;
    right: 16px;
}
ul li:nth-child(4){
     position: relative;
    right: 24px;
}

</style>