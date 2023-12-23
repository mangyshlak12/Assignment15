<template>
    <ul>
    <li v-for="(item,index) in items" :key="index">{{item}}</li>
    </ul>
</template>
<script>
export default {
    data(){
        return{
            items: [
                'NoteBook',
                'Iphone',
                'Samsung',
                'Assorti Doner',
                'Water'
            ]
        }
    }
}
</script>
<style scoped>
ul{
    list-style: none;
}
</style>