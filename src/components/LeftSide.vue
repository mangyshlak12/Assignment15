<template>
      <div class="left__container">
        <div class="header__left">
          <div class="header__left__content">
              <Icons :link="facebookImage" name="hola"/>
            <div>
              <TextType name="fillow" text="fillow."/>
              <br>
              <TextType name="below__fillow" text="Saas Admin Dashboard"/>
            </div>
          </div>
        </div>

        <div class="menu__title">
            <TextType name="main__menu" text="Main Menu"/>
        </div>
        
        <div class="content__left">
          
            <div class="content__left__container">
              
              <NavigationLinks :pagePath="pagesList" :images="listNavImages"/>
            </div>
        </div>
        <div class="user__left">
            <div>
              <Icons :link="Avatar" name="avatar"/>
            </div>
            <div class="author__information">
              <TextType name="author__name" text="Levi Siregar"/>
              <br>
              <TextType name="author__email" text="leviregar@mail.com"/>
            </div>
            
        </div>

        <div class="progress__left">
            <div class="progress__wrapper"> 
              <div class="progress__wrapper__content">
                <Icons :link="Star" name=""/>
              <TextType name="progress" text="Task Progress"/>
              </div>
              <div>
                20/45
              </div>
              
            </div>
            <div>
                <ProgressBar/>
            </div>
        </div>
        <div class="footer__left">
            <TextType text="Fillow Saas Admin" name="footer__left__admin"/>
              <br>
            <TextType text="© 2020 All rights Reserved" name="footer__left__option"/>
            <div class="footer__left__last">Made with <span class="heart"><img src=".././Assets/heart.svg" alt=""></span> by Peterdaw</div>


        </div>
      </div>
</template>
<script>
import Icons from './Content/icons.vue';
import ProgressBar from './Content/ProgressBar.vue';
import NavigationLinks from './Navigation/NavigationLinks.vue';
import TextType from './Others/TextType.vue';

import facebookImage from '.././Assets/facebook.png';
      import Homeimage from '.././Assets/home.svg';
      import lighting from '.././Assets/lighting.svg';
      import contact from '.././Assets/contact.svg';
      import canvan from '.././Assets/canvan.svg'
      import Analytics from '.././Assets/Analytics.svg'
      import Calendar from '.././Assets/calendar.svg';
      import Message from '.././Assets/message.svg';
      import Avatar from '.././Assets/UA8.png';
      import Star from '.././Assets/star.svg';

export default {
    components:{
        Icons,
        ProgressBar,
        NavigationLinks,
        TextType
    },
    props:['pages'] , 
    data(){
        return{
             facebookImage,
          listNavImages: [
            Homeimage,
            lighting,
            contact,
            canvan,
            Analytics,
            Calendar,
            Message
          ],
          Avatar,
          Star,
          pagesList: this.pages
        }
    },
}
</script>
<style scoped>
*{
    padding: 0;
    margin: 0;
    box-sizing: border-box;
}
.header__left{
  display: flex;
  justify-content: center;
  align-items: center;
  margin-left: 10px;
}
.header__left__content{
  display: flex;
  gap: 20px;
}
.container{
  display: flex;
}
.left__container{
  width: 19%;
  padding: 15px 0px 0px 0px;
  border-right: 1px solid #d9e1cc;
}
.menu__title{
  margin-top: 30px;
  margin-left: 30px;
}
.content__left{
  margin-top: 15px;
}
.user__left{
  margin-top: 20px;
  display: flex;
  padding-left: 20px;
  gap: 10px;
}
.author__information{
  padding-top: 5px ;
}
.progress__left{
  font-size: 12px;
  
  width: 85%;
  margin: 20px auto;
}
.progress__wrapper{
  display: flex;
  width: 85%;
  justify-content: space-between;
  margin-bottom: 5px;
}
.progress__wrapper__content{
  display: flex;
  gap: 5px;
}
.footer__left{
  margin-top: 60px;
  padding-left: 25px ;
}
.footer__left__last{
  margin-top: 20px;
  font-size: 14px;
  color: #96A0AF;
}
.heart{
  position: relative;
  top: 3px;
}
</style>