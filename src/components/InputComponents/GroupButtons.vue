<template>
    <div class="select">
        <div class="option" v-for="(option,index) in options" :key="index" :class="{'active':option.isSelected, 'option': !option.isSelected}" @click="isChoosen(index)">{{option.option}}</div>
       
    </div>
    
</template>
<script>
export default {
    data(){
        return{
            options: [{
                isSelected: false,
                option: 'Option1'
            },
            {
                isSelected: false,
                option: 'Option2'
            },
            {
                isSelected: false,
                option: 'Option3'
            }
            ]
       
        }
    },
         methods:{
                isChoosen(index){
                    this.options.map(option=>{
                        option.isSelected = false;
                    });
                    this.options[index].isSelected = true;
                }
            }
}
</script>
<style scoped>
    .select{
        display: flex;
        align-items: center;
        justify-content: center;
    }
    .option{
        border: 1px solid black;
        padding: 5px 10px;
        border-radius: 5px;
        cursor: pointer;
    }
    .option:hover{
        transform: scale(1.1);
    }
    .active{
        background: #d9e1cc;
    }
</style>