<template>
    <div class="tagcontainer">
        <span v-for="(item,index) in items" :key="index" class="item">{{item.title}}
            <span class="remove" @click="removeItem(item.date)">x</span>
        </span>
    </div>
</template>
<script>
export default {
    data(){
        return{
            items: [
                {
                    title: 'Item 1',
                    date: new Date()
                },
                 {
                    title: 'Item 2',
                    date: new Date()
                },
                 {
                    title: 'Item 3',
                    date: new Date()
                },
                 {
                    title: 'Item 4',
                    date: new Date()
                },
                {
                    title: 'Item 5',
                    date: new Date()
                },
                {
                    title: 'Item 6',
                    date: new Date()
                },
                {
                    title: 'Item 7',
                    date: new Date()
                },
                {
                    title: 'Item 8',
                    date: new Date()
                }

            ]
        }
    },
    methods:{
        removeItem(date){
            this.items = this.items.filter(item=>item.date!==date);
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
.tagcontainer{
    display: flex;
    flex-wrap: wrap;
    width: 30%;
    gap: 20px;
    border: 1px solid #d9e1cc;
}
.remove{
    content: 'x';
    color: red;
    font-size: 18px;
    margin-left: 5px ;
    cursor: pointer;
}
.remove:hover{
    background-color: #d9e1cc;
}

</style>