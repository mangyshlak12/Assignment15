<template>
    <button :class="clas" :style="{color: col}">{{name}}</button>    
</template>
<script>
export default {
    props:{
        name:{
            type:String,
            required:true
        },
        clas:{
           type:String,
           required: true 
        },
        col:{
            type:String,
            required: true
        }
    }
}
</script>
<style scoped>
.fButton{
border: none;
padding: 9px 10px;
border-radius: 20px;
 font-weight: 600;
 cursor:pointer;

}
.fButton:hover{
    background: gray;
    opacity: 0.4;
}
.view{
    color: rgb(87, 35, 155);
    border: 1px solid #d9e1cc;
    padding: 10px 20px;
    border-radius: 35px;
    cursor: ponter;
}
.newmessage{
    color: white;
    font-weight: 600;
    background: rgb(136, 97, 180);
    padding: 10px 23px;
    outline: none;
    border: none;
    border-radius: 20px;
}
.display{
    background-color: #d9e1cc;
    padding: 10px 15px;
    border: none;
    border-radius: 15px;

}
</style>