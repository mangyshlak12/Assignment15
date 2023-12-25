<template>
        <div class="content">
            <div class="information">
                 <div class="author__information">
                <div><Icons :link="item.src" name="avatarrr"/></div>
                <div>
                    <span class="author__name">{{item.name}}</span>
                    <br>
                    <span class="author__message">{{item.message}}</span>
                </div>
                 </div>
                 <div class="content__information">
                    <div class="lastseen">{{item.lateseen}}</div>
                    <div><Icons :link="Dots"/></div>
                 </div>
            </div>
           
        </div>
</template>
<script>
import Icons from './Content/icons.vue';
import Dots from '../Assets/3dots.svg';
export default {
    components:{
        Icons
    },
    data(){
        return{
            Dots
        }
    },
    props:{
        item:{
            type: Object,
            required:true
        }
    }
}
</script>
<style scoped>
.content{
    margin-top: 20px;
    border-bottom: 1px solid #d9e1cc;
    padding-bottom: 10px ;
}
.author__information{
    display: flex;
    gap: 15px;
    align-items: center;
}
.information{
    display: flex;
    justify-content: space-between;
    align-items: center ;
}
.author__name{
    position: relative;
    font-weight: 600;
    top: -2px
}
.content__information{
    font-size: 8px;
    display: flex;
    align-items: center;
    gap: 10px;
    
}
.lastseen{
    position: relative;
    top: 12px;
}
</style>