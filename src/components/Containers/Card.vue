<template>
    <div class="card">
        <div class="title">{{title}}</div>
        <div class="content">{{content}}</div>
        </div>    
</template>
<script>
export default {
    data(){
        return{
            title: 'Title1',
            content: 'Content1'
        }
    }
}
</script>
<style scoped>
.card{
    border-radius: 5px;
    width: 200px;
    padding: 5px;
    background: #d9e1cc;

}
.title{
    font-size: 20px;
    margin-bottom: 5px;
}
</style>