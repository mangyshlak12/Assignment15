<template>
<div class="container">
    <div class="title">
        <span>Task1</span>
        <span v-if="!isClicked" class="sign" @click="clickSign()">+</span>
        <span v-if="isClicked" class="sign" @click="clickSign()">-</span>
    </div>   
    <div :class="{'content': isClicked, 'reactive': !isClicked}">
            Lorem ipsum dolor, sit amet consectetur adipisicing elit. Sit praesentium eos at architecto voluptatibus aspernatur porro modi voluptas nostrum debitis deserunt, fugit, consequuntur tenetur accusamus veritatis recusandae obcaecati, expedita quas.
    </div>
</div>
     
</template>
<script>
export default {
    data(){
        return{
            isClicked: false
        }
    },
    methods:{
        clickSign(){
            this.isClicked = !this.isClicked;
        }
    }
    
}
</script>
<style scoped>
.container{
    width: 400px;
    line-height: 1.2;
}
.content{
    height: 150px;
    transition: 0.5s;
    overflow: hidden; 
}
.reactive{
    height: 0;
    overflow: hidden;
    transition: 0.5s;

}
.title{
    background: #d9e1cc;
    display: flex;
    justify-content: space-between;
    padding: 5px 5px;
    align-items: center;
}
.sign{
    font-size: 24px;
    font-weight: 600;
    cursor: pointer;
    padding: 0px 5px;
}
.sign:hover{
    background: gray;
    opacity: 0.3;
}
</style>