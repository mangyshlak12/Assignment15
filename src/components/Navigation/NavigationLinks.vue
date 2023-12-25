<template>
    <ul class="listContainer">
          <li v-for="(item,index) in menu" :key="index" @click="clicktoNav(index)" :class="{'active': checkToSelect(index)}">
            <span v-if="checkToSelect(index)" class="beforeA"></span>
                <div>
                <a :href="toCheck(index)">
                    <Icons :link="images[index]" name=""/>
                    {{item.title}}
                </a>
            </div>
         </li>  
        
    </ul>    
</template>
<script>
import Icons from '../Content/icons.vue'

export default {
    data(){
        return{
            menu: [
                {
                   title: 'DashBoard',
                   isClicked: false
                },
                {
                   title: 'Project',
                   isClicked: false
                },
                {
                   title: 'Contacts',
                   isClicked: false
                },
                {
                   title: 'Kanban',
                   isClicked: false
                },
                {
                   title: 'Analytics',
                   isClicked: false
                },
                {
                   title: 'Calendar',
                   isClicked: false
                },
                {
                   title: 'Messages',
                   isClicked: false
                },

               
                
            ]
        }
    },
    props:['pagePath' , 'images'],
    methods:{
        clicktoNav(index){
            console.log(this.pages);
            console.log('hello')
            this.menu.map(item=>{
                item.isClicked = false;
            })
            this.menu[index].isClicked = true;
        },
        toCheck(index){
            if(index===0){
                return this.pagePath[0].name;
            }else if(index ===1 ){
                 return this.pagePath[1].name;   
            }else if(index === 2 ){
                return this.pagePath[2].name;
            }else if(index == 3){
                return this.pagePath[3].name;
            }else if(index == 4){
                return this.pagePath[4].name;
            }else{
                return '';
            }
        }
        ,
        checkToSelect(index){
            if(index===0){
                return this.pagePath[0].isSelected;
            }else if(index ===1 ){
                 return this.pagePath[1].isSelected;   
            }else if(index === 2 ){
                return this.pagePath[2].isSelected;
            }else if(index == 3){
                return this.pagePath[3].isSelected;
            }else if(index == 4){
                return this.pagePath[4].isSelected;
            }else{
                return false;
            }
        }
    },
    components:{
        Icons
    }
}
</script>
<style scoped>
*{
    padding: 0;
    margin: 0;

}
.listContainer{
    gap: 20px;
    list-style: none;
}
ul li div{
     padding-left: 30px;
}
ul li{
    display: flex;
   width: 75%;
   margin-bottom: 10px;
}
ul li a{
    padding: 10px 0px;
    border-radius: 5px;
    display: flex;
     gap: 25px;
     color: '#96A0AF';
    text-decoration: none;
    color: black;
}
ul li a:hover{
    border-bottom: 1px solid #886cc0;
}
ul li:nth-child(2) a::after{
    content: '67';
    color: white;
    background: green;
    opacity: 0.8;
    padding: 0px 6px;
    border-radius: 10px;
    font-size: 12px;
    padding-top: 2px;
    font-weight: 600;
    position: relative;
    left: -10px;
} 
ul li:nth-child(5) a::after{
    position: relative;
    left: -10px;
    content: '12';
    color: white;
    background: orangered;
    opacity: 0.6;
    padding: 0px 6px;
    border-radius: 10px;
    font-size: 12px;
    font-weight: 600;
    padding-top: 2px;
}
.active a img{
    fill:#886cc0;
}
.active a {
    color: #886cc0;
}
.beforeA{
    width: 6px;
    display: block;
    background: #886cc0;
    height: 40px;
    border-top-right-radius: 3.563rem ;
    border-bottom-right-radius: 3.563rem;
}

</style>