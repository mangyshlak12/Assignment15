<template>
    <ul>
        <li v-for="(item,index) in buttons" :key="index" :class="{'active': item.isSelected}" @click="check(item)">
            <Icons v-if="item.src!==''" :link="item.src"/>
            <p>{{item.title}}</p>
        </li>
    </ul>
</template>
<script>
import Icons from './icons.vue'

export default {
    props:{
        buttons:{
            type: Object,
            required: true
        }
    },
    components:{
        Icons
    },
    methods:{
        check(item){
            this.buttons.map(item=>{
                item.isSelected=false;
        })
            item.isSelected =!item.isSelected;
        }
    }
}
</script>
<style scoped>
*{
    padding: 0;
    margin: 0;
    box-sizing: border-box;
}
ul{
    display: flex;
    gap: 5px;
}
ul li{
    display: flex;
    gap: 10px;
    list-style: none;
    border: 1px solid #d9e1cc;
    padding: 5px 15px;
    font-size: 14px;
    border-radius: 20px;
    cursor: pointer;
}
.active{
    background: #d9e1cc;
}
</style>