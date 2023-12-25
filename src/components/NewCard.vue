<template>
    <div v-if="name===0" class="content"> 
        <div class="content__wrapper">
            <div class="wrapper__left">
                <div class="title">Total Clients</div>
            <div class="information">
                <span class="number">68</span>
                <div class=""><span class="caret"></span>
                <span class="percentage">
                    +0.5%</span></div>  
            </div>
            </div>
            <div class="wrapper__right">
                <img :src="LineVertical" alt="">
            </div>
          
        </div>
     </div>    
      <div v-if="name===1" class="content"> 
        <div class="content__wrapper">
            <div class="wrapper__left">
                <div class="title">Total Clients</div>
            <div class="information">
                <span class="number">68</span>
                <div class=""><span class="caret"></span>
                <span class="percentage">
                    +0.5%</span></div>  
            </div>
            </div>
            <div class="wrapper__right">
                <img :src="LineVertical" alt="">
            </div>
          
        </div>
     </div>    
      <div v-if="name===2" class="content"> 
        <div class="content__wrapper">
            <div class="wrapper__left">
                <div class="title">Total Clients</div>
            <div class="information">
                <span class="number">68</span>
                <div class="">
                <span class="caret"></span>
                <span class="percentage">
                    +0.5%</span>
                 </div>  
            </div>
            </div>
            <div class="wrapper__right">
                <img :src="LineVertical" alt="">
            </div>
          
        </div>
     </div>    
      <div v-if="name===3" class="content"> 
        <div class="content__wrapper">
            <div class="wrapper__left">
                <div class="title">Total Clients</div>
            <div class="information">
                <span class="number">68</span>
                <div class=""><span class="caret"></span>
                <span class="percentage">
                    +0.5%</span></div>  
            </div>
            </div>
            <div class="wrapper__right">
                <img :src="LineVertical" alt="">
            </div>
          
        </div>
     </div>    
</template>
<script>
import LineVertical from '../Assets/LinesVertical.svg';
export default {
    props:{
        item:{
            type:Object,
            required:true
        },
        name: {
            type: Number,
            required:true
        }
    },
    data(){
        return{
            LineVertical
        }
    }
}
</script>
<style scoped>
.content{
    display: flex;
    padding: 20px;
    border-radius: 10px;
    background: white;
    width: 190px;
}
.content__wrapper{
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
}
.information{
    display: flex;
    margin-top: 15px ;
    gap: 15px;
    align-items: center;
}
.title{
    font-size: 14px;
    font-weight: bold;   
}
.number{
    font-weight: bold;
    font-size: 24px;
}
.percentage{
    font-weight: 600;
    color: green;
    font-size: 14px;
}
.caret{
    width: 0;
    height: 0;
    border-left: 7px solid transparent;
    border-right: 7px solid transparent;
    border-bottom: 8px solid #008000;
    position: relative;
    top: -27px;
    left: 18px;
}


</style>