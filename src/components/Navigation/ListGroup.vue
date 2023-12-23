<template>
    <ul v-for="(i,index) in count" :key="index" class="listcontainer">
        <li v-for="(item,index) in items" :key="index">{{item}}</li>
    </ul>
</template>
<script>
export default {
    data(){
        return{
            items: [
                'Item 1',
                'Item 2',
                'Item 3',
                'Item 4',
                'Item 5',
                'Item 6'
            ],
            count: [1,2,3]
        }
    }
}
</script>
<style scoped>
.listcontainer{
    margin-top: 20px;
}
</style>