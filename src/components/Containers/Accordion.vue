<template>
<div class="contain">
    <div class="title">
        <span>{{item.title}} ({{item.count}})</span>
        <span v-if="!isClicked" class="sign" @click="clickSign()">+</span>
        <span v-if="isClicked" class="sign2" @click="clickSign()">-</span>
    </div>   
       
    <div v-for="(con, index) in content" :key="index" :class="{'content': isClicked, 'reactive': !isClicked}">
            
        <div class="content__header">
            <div class="header__left">
                <div class="circle" :style="{background: con.color, color: con.color}"></div>
                <span class="aim" :style="{color: con.color}">{{con.aim}}</span>
           </div>
           <div class="header__right">
            <Icons :link="Dots" name="rotate"/>
           </div>
        </div>
        <div class="content__text">
            {{con.text}}
        </div>
        <div class="content__bar">
            <CanvanAccordionPrBar :color="con.color" :progress="con.progress"/>
        </div>
         <div class="content__details">
            <div><ListImages :images="con.images1" name="av"/></div>
            <div class="content__footer"> 
                <img :src="Time" alt="" class="img">
                <div class="footer__text">Due in 4 days</div>
            </div>
         </div>
    </div>
</div>
     
</template>
<script>
 import Icons from '../Content/icons.vue';
 import CanvanAccordionPrBar from '../Content/CanvanAccordionPrBar.vue';
 import Dots from '../../Assets/3dots.svg'
import ListImages from '../ListImages.vue';
    import Time from '../../Assets/time.svg';
    
export default {
    data(){
        return{
            isClicked: false,
            Dots,
            Time
            
        }
    },
    methods:{
        clickSign(){
             console.log(this.content === null);
            this.isClicked = !this.isClicked;
           
        },
         
    },
    components:{
        Icons,
        CanvanAccordionPrBar,
        ListImages
        
    } ,
    props: {
        item:{
            type:Object,
            required:true
        },
        content:{
            type:Object,
            required:true
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
.contain{
    width: 400px;
    line-height: 1.2;
    display: block;
}
.content{
    
    transition: 0.5s;
    overflow: hidden; 
    background: white;
    padding: 15px;
    border-radius: 10px;
    margin-top: 20px ;
}
.reactive{
    height: 0;
    overflow: hidden;
    transition: 0.5s;

}
.aim{
    font-size: 11px;
}
.title{
    font-weight: 700;
    font-size: 18px;
    display: flex;
    justify-content: space-between;
    padding: 5px 5px;
    align-items: center;
}
.circle{
    width: 12px;
    height: 12px;
    font-size: 14px;
   
    border-radius: 50%;
    
}
.content__text{
    margin: 13px 0px;
    font-weight: 600;
    font-size: 18px;
}
.header__left{
    display: flex;
    gap: 10px;
    ;
    align-items: center;
}
.sign{
    font-size: 24px;
    font-weight: 600;
    cursor: pointer;
    padding: 2px 10px;
    color: rgb(99, 58, 165);
    font-weight: bold;
    background: #d9e1cc;
    border-radius: 50%;
}
.sign2{
 font-size: 24px;
    font-weight: 600;
    cursor: pointer;
    padding: 1px 11px;
    color: rgb(99, 58, 165);
    font-weight: bold;
    background: #d9e1cc;
    border-radius: 50%;
}
.sign:hover{
    background: gray;
    opacity: 0.3;
}
.content__header{
    display: flex;
    justify-content: space-between;
}
.content__details{
    margin-top: 15px;
     display: flex;
     justify-content: space-between;

}
.content__footer{
    display: flex;
    font-size: 11px;
    color: gray;
    align-items: center;
    gap: 5px;
}
.img{
    width: 16px;
}
.footer__text{
width: 70px;
}
.Alternative{
    margin-top: 20px ;
    background: white;
    padding: 20px;
}
.alternative__content{
    background: #d9e1cc;
    font-size: 14px;
    color:gray;
}
</style>