<template>
    <ul class="listContainer" v-for="(item,index) in count" :key="index">
        <li v-for="(item,index) in menu" :key="index"><a href="" >{{item}}</a></li>
    </ul>    
</template>
<script>
export default {
    data(){
        return{
            menu: [
                'Main',
                'Shop',
                'Contact',
                'Profile'
            ],
            count: [1,2,3]
        }
    }
}
</script>
<style scoped>
.listContainer{
    display: flex;
    gap: 20px;
    list-style: none;

}
ul li a{
    text-decoration: none;
    color: black;
}
ul li a:hover{
    border-bottom: 1px solid red;
}
</style>