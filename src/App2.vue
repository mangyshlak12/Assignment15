<template>
    <div class="container">
        <LeftSide :pages="pages"/>
            <div class="right__container">
                <Header/>
                <div class="body">
                    <div class="body__first">
                        <GroupProjectButtons :project="projects" />
                        <div class="first__right">
                            <div><Button name="+ New Project" class="newmessage"/></div>
                            <div><Icons :link="Mail"/></div>
                            <div><Icons :link="Canvan"/></div>
                        </div>
                    </div>    
                   
                </div>
            </div>
    </div>
</template>
<script>
import Header from './components/Content/header.vue';
import GroupProjectButtons from './components/GroupProjectButtons.vue';
import Button from './components/InputComponents/Buttons/Button.vue';
import LeftSide from './components/LeftSide.vue';
import Mail from './Assets/Mail.svg';
import Canvan from './Assets/Canvan1.svg'

import Icons from './components/Content/icons.vue';
import Avatar from './Assets/UA8.png';
export default {
components:{
    LeftSide,
    Header,
    GroupProjectButtons,
    Button,
    Icons,
   
},
data(){
    return{
          pages:[
            {
              name: 'index.html',
              isSelected: false
            },
             {
              name: 'index2.html',
              isSelected: true
            },
             {
              name: 'index3.html',
              isSelected: false
            },
             {
              name: 'index1.html',
              isSelected: false
            },
            {
              name: 'index4.html',
              isSelected: false
            }

          ],
          Mail, Canvan,
          projects:[
            {
                title: 'Redesign Owlio Landing Page Web..',
                src: Avatar,
                display: 'PENDING',
                color: 'orange'
            
    
            },
            {
                title: 'Redesign Owlio Landing Page Web..',
                src: Avatar,
                display: 'ON PROGRESS',
                color: 'blue'
            },
            {
                title: 'Redesign Owlio Landing Page Web..',
                src: Avatar,
                display: 'CLOSED',
                color: 'green'
            },
            {
                title: 'Redesign Owlio Landing Page Web..',
                src: Avatar,
                display: 'ON PROGRESS',
                color: 'blue'
            },
            {
                title: 'Redesign Owlio Landing Page Web..',
                src: Avatar,
                display: 'PENDING',
                 color: 'orange'
            }

          ]
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
.container{
    display: flex;

}
.right__container{
    width: 81%;
}
.body{
    padding: 30px;
    background: #f3f0f9;
    height: 100%;
}
.body__first{
    display: flex;
    align-items: center;
    justify-content: space-between;    
}
.first__right{
    display: flex;
    gap: 20px;
    align-items: center;
}
</style>