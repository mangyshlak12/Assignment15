<template>
    <div class="containe">
            <LeftSide :pages="pages"/>
      
      <div class="right__container">
            <Header/>
        <div class="container__bodies">
            <div class="body">
                <div class="body__header">
                    <div class="body__header__left">
                        <span class="body__header__title">Fillow Company Profile Website Phase 1</span>
                        <br>
                        <span class="body__header__content">Created by <span class="author">Hajime Mahmude</span>  n on June 31, 2020</span>            
                    </div>
                    <div class="body__header__right">
                        <div>
                            <span class="body__header__title">Fillow Studios</span>
                            <br>
                            <span class="right__content">Software House</span>
                        </div>
                        <div class="avatar__holder"><Icons :link="Facebook" name="avatarr"/></div>
                        <div @click="check()"><Icons :link="Dots"/></div>
                    </div>  
                </div>

                <div class="body__footer">
                     <div class="footer__left">
                            <div class="listimages">
                                <ListImages :images="images" name="first"/>
                            </div>
                            <div class="listButtons">
                                <ListButtons :buttons="buttons"/>
                            </div>
                    </div>
                    <div class="footer__right">
                        <div class="content">
                            Total Progress 60%
                            <div class="progress">
                                <CanvanProgressBar/>
                            </div>
                         </div>
                    </div>
                </div>
            </div>

            <div class="body__second">
                <Accordion v-for="(item,index) in accordions" :key="index" :item="item" :content="getContentByIndex(index)" />   
            </div>
            </div>  
      </div>

    </div>   
</template>
<script>
import Header from './components/Content/header.vue';
import LeftSide from './components/LeftSide.vue';

    import ListButtons from './components/Content/ListButtons.vue';
    import CanvanProgressBar from './components/Content/CanvanProgressBar.vue';
    import Accordion from './components/Containers/Accordion.vue';
    import Dots from './Assets/3dots.svg';
    import Facebook from './Assets/facebook.png';
    import Icons from './components/Content/icons.vue';
    import Avatar from './Assets/UA8.png';
    import canvanMessage from './Assets/canvanMessage.svg';
    import AddUser from './Assets/Adduser.svg';
    import ListImages from './components/ListImages.vue';
    export default {
        components:{
            Header,
            LeftSide,
            Icons,
            ListButtons,
            CanvanProgressBar,
            Accordion,
            ListImages    
        },
        data(){
            return{
                Dots,
                Facebook,
                images: [
                    Avatar,
                    Avatar,
                    Avatar,
                    Avatar
                ],
                buttons:[
                    {
                        src: AddUser,
                        title: 'Invite People',
                        isSelected: true
                    },
                    {
                        src: '',
                        title: 'Edit',
                        isSelected: false
                    },
                    {
                        src: '',
                        title: 'Private',
                        isSelected:false
                    },
                    {
                        src:  canvanMessage,
                        title: '45 comments',
                        isSelected: false
                    } 
                    
                ],
                accordions:[
                    {
                        title: 'To-Do List',
                        count: '24'
                    },
                    {
                        title: 'On Progress',
                        count: '2'
                    },
                    {
                        title: 'Done',
                        count: '3'
                    },
                    {
                        title: 'Revised',
                        count: '0'
                    }
                ],
                content: 
                    {
                    row1: {
                    col1:{
                        aim: 'DESIGN    ',
                        text: 'Create wireframe for landing page phase 1',
                        color: 'purple',
                        images1: 
                        [
                        Avatar,
                        Avatar,
                        Avatar
                        ],
                        progress: 30
                    },
                    col2:{
                        aim: 'IMPORTANT',
                        text: 'Visual Graphic for Presentation to Client',
                        color: 'yellow',
                        images1: 
                        [
                        Avatar,
                        Avatar,
                        Avatar,
                        Avatar
                        ],
                        progress: 20
                    },
                    col3:{
                        aim: 'DATABASE',
                        text: 'Setup database for create API connection',
                        color: 'green',
                        images1: 
                        [
                        Avatar,
                        Avatar
                        ],
                        progress: 18
                    }  
                    },
                    row2: {
                        col1:{
                            aim: 'UPDATE',
                        text: 'Update information in footer section',
                        color: 'green',
                        images1: 
                        [
                        Avatar,
                        Avatar,
                        Avatar,
                        Avatar
                        ],
                        progress: 100
                        },
                        coll2:{
                        aim: 'VIDEO',
                        text: 'Motion Graphic Video Promotion for Advertising',
                        color: 'lightblue',
                        images1: 
                        [
                        Avatar,
                        Avatar,
                        Avatar
                        ],
                        progress: 80
                        }
                    },
                    row3:{
                        col1:{
                        aim: 'BUGS FIXING',
                        text: 'Button contact not working when clicked',
                        color: 'red',
                        images1: 
                        [
                        Avatar,
                        Avatar,
                        Avatar,
                        Avatar
                        ],
                        progress: 100
                        },
                        col2:{
                        aim: 'BUGS FIXING',
                        text: 'BUGS report from user testing [25 points]',
                        color: 'red',
                        images1: 
                        [
                        Avatar,
                        Avatar,
                        Avatar,
                        Avatar
                        ],
                        progress: 95
                        },
                        coll3:{
                        aim: 'HTML',
                        text: 'Create base html project landing page',
                        color: 'pink',
                        images1: 
                        [
                        Avatar,
                        Avatar,
                        Avatar,
                        Avatar
                        ],
                        progress: 100
                        }
                    },
                    row4:{
                        
                    }
                    },
                     pages:[
            {
              name: 'index.html',
              isSelected: false
            },
             {
              name: 'index2.html',
              isSelected: false
            },
             {
              name: 'index3.html',
              isSelected: false
            },
             {
              name: 'index1.html',
              isSelected: true
            },
            {
              name: 'index4.html',
              isSelected: false
            }

          ]

                    
                    

                

                
            }
        
        },
    methods:{
        check(){
            console.log(this.content.isEmpty());
        },
         getContentByIndex(index) {
     
      switch (index) {
        case 0:
          return this.content.row1;
        case 1:
          return this.content.row2;
        case 2:
          return this.content.row3;
       
        default:
          return {}; 
      }
    },
    }
    
}
</script>
<style scoped>
*{
    padding: 0;
    margin: 0;
    box-sizing: border-box;
}
.containe{
    display: flex;
}
.right__container{
    width: 81%;
}
.container__bodies{
background-color: #f3f0f9 ; 
     padding: 30px 30px 0px;
    height: 100%;
}
.body{
  background: white;
  padding: 20px;
}
.body__header{
    display: flex;
    justify-content: space-between;
}
.body__header__title{
    font-weight: 700;
    font-size: 19px;
}
.body__header__content{
    font-size: 12px;
    font-weight: 600;
    color: #96A0AF;
    position: relative;
    top: 15px;
}
.author{
    color: gray;
}
.body__header__right{
    display: flex;
    gap: 14px;
    align-items: center;
}
.avatar__holder{
    border: 1px solid rgb(99, 58, 165);
    padding: 5px 7px;
    border-radius: 10px;
}
.right__content{
     font-size: 12px;
    font-weight: 600;
    color: #96A0AF;
    position: relative;
    
}
.body__footer{
    display: flex;
    align-items: center;
    margin-top: 20px;
    justify-content: space-between;
}
.footer__left{
    display: flex;
    align-items: center;
}

.content{
    font-size: 14px;
    font-weight: 600;
    display: flex;
    align-items: center;
    gap: 10px;
    
}
.body__second{
    display: flex;
    margin-top: 20px;
    padding: 10px 0px;
    gap: 20px;
}
</style>