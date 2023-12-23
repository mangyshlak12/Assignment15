<template>
    <span :class="name">{{text}}</span>    
</template>
<script>
export default {
    props:{
        name:{
            type: String,
            required: true
        },
        text:{
            type:String,
            required:true
        },
       
    }
}
</script>
<style scoped>
.fillow{
    font-weight: 600;
    font-size: 26px;
}
.belowfillow{
    font-size: 12px;
    color: #96A0AF;
}
.main__menu{
    font-size: 12px;
    font-weight: 600;
    color: #d9e1cc;
}
.author__name{
    font-weight: 700;
    font-size: 14px;
}
.author__email{
    font-size: 10px;
    padding-top: 5px;
}
.footer__left__admin{
    font-size: 12px;
    font-weight: 600;
}
.footer__left__option{
      color: #96A0AF;
      font-size: 12px;
}
</style>