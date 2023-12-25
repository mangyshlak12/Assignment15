<template>
    <div class="card">
        <div class="container">
            <div class="card__information">
                 <div class="card__avatar"><Icons :link="src" name="avatar"/></div>
                 <div>
                    <span class="card__question"
                >{{question}}</span>
                    <br>
                    <span class="card__content">{{content}}</span>
                 </div>
            </div>
            <div class="card__pin" :class="{'active': isPressed}" @click="check(isSelected)">
                <Icons :link="Pin"/>
            </div>
           
        </div>
    </div>    
</template>
<script>
import Icons from '../Content/icons.vue';
import Pin from '../../Assets/pin.svg';
export default {
    data(){
        return{
           Pin,
           isPressed: this.isSelected
        }
    },
    props:{
        src:{
            type: String,
            required: true
        },
        question:{
            type: String,
            required: true
        },
        content:{
            type: String,
            required: true
        },
        isSelected:{
            type: Boolean,
            required: true
        }
    
    },
    components:{
        Icons
    },
    methods:{
        check(){
           this.isPressed = !this.isPressed;
        }
    }
}
</script>
<style scoped>
.card{
    border-radius: 5px;
    width: 100%;
    border-bottom: 1px solid #d9e1cc;
    padding: 10px 0px 5px 0px;
}
.container{
    padding-top: 5px;
    padding-bottom: 20px;
    display: flex;
    justify-content: space-between ;
    width: 100%;
}
.card__information{
    display: flex;
    gap: 15px;
    align-items: center;
}
.card__question{
    font-size: 14px;
    font-weight: bold;
    position: relative;
    top: -5px;  
}
.card__pin{
   position: relative;
   border: 1px solid rgb(87, 35, 155);
   display: flex;
   align-items: center;
   padding: 10px 12px;
   height: 80%;
   border-radius: 10px;
}
.active{
    background: #d9e1cc;
}

</style>