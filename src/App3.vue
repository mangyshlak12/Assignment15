<template>
    <div class="container">
        <LeftSide :pages="pages"/>
            <div class="right__container">
                <Header/>
                <div class="body">
                    <div class="body__header">
                        <div class="header__left">
                            <SearchBar name="asset"/>
                        </div>
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
import LeftSide from './components/LeftSide.vue';
import SearchBar from './components/Navigation/SearchBar.vue';
import Icons from './components/Content/icons.vue';
import Button from './components/InputComponents/Buttons/Button.vue';
import Mail from './Assets/Mail.svg';
import Canvan from './Assets/Canvan1.svg'

import Contacts from './components/Contacts.vue';


export default {
components:{
    LeftSide,
    Header,
    SearchBar,Icons,Button,
    Contacts
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
              isSelected: false
            },
             {
              name: 'index3.html',
              isSelected: true
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
          Mail,Canvan,
          count: [
            0,1,2,3,4,5,6,7,8,9,10,11
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
.body__header{
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.first__right{
    display: flex;
    gap: 10px;
    align-items: center;
}
.body__content{
    display: flex;
    flex-wrap: flex;
    margin-top: 50px ;
   
}
.content{
    width: 400px;
}
</style>