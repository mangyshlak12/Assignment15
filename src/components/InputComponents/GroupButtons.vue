<template>
    <div class="select">
        <div class="option" v-for="(option,index) in options" :key="index" :class="{'active':option.isSelected, 'option': !option.isSelected}" @click="isChoosen(index)">{{option.option}}</div>  
    </div>
    
</template>
<script>
export default {
    data(){
        return{
           
       
        }
    },
         methods:{
                isChoosen(index){
                    this.options.map(option=>{
                        option.isSelected = false;
                    });
                    this.options[index].isSelected = true;
                }
    },
        props:{
            options:{
                type: Object,
                required:true
            }
        }
}
</script>
<style scoped>
    .select{
        display: flex;
        align-items: center;
        justify-content: center;
        background: #d9e1cc;
        border-radius: 20px;

    }
    .option{
        font-size: 12px;
        padding: 10px 15px;
        border-radius: 20px;
        font-weight: 600;
        color: #96A0AF;
        cursor: pointer;
    }
    .option:hover{
        transform: scale(1.1);
    }
    .active{
        background: white;
        color: black;
        font-weight: 700;
        position: relative;
    }
   

</style>