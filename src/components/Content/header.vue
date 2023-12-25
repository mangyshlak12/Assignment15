<template>
    <div class="header">
        <div class="header__wrapper">
             <div class="header__wrapper__left">
                <div><Icon :link="Canvan1"/></div>
                <div class="title">Dashboard</div>
            </div>
            <div class="header__wrapper__right">
                    <div class="wrapper__right__search"><SearchBar name="img"/></div>
                    <div class="wrapper__right__navbar"><SlideBar :images="images"/></div>
                    <div class="wrapper__right__options">
                        <div class="options__img"><Icon :link="Avatar" name="avatar"/></div>
                        <div><DropDown selectedItem="EN"/></div>
                    </div>
            </div>
        </div>
      

    </div>    
</template>
<script>
    import Icon from './icons.vue';
    
    import Canvan1 from '../../Assets/Canvan1.svg';
    import DropDown from '../InputComponents/Buttons/DropDown.vue';
    import SearchBar from '../Navigation/SearchBar.vue';
    import SlideBar from './SlideBar.vue';

    import Avatar from '../../Assets/UA8.png'
    import Settings from '../../Assets/Settings.svg';
    import Mail from '../../Assets/Mail.svg';
    import Calendar1 from '../../Assets/Calendar1.svg';
    import Notification from '../../Assets/Notification.svg';
    import Star from '../../Assets/star1.svg';

export default {
    components:{
        Icon,
        DropDown,
        SearchBar,
        SlideBar
    },
    data(){
        return{
            Canvan1,
            Avatar,
            images: [
                 Star,
                 Notification,
                 Mail,
                 Calendar1,
                 Settings           
                 
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
.header{
    padding: 30px 25px 15px;
    border-bottom: 1px solid #d9e1cc;
   
}
.header__wrapper{
    display: flex;
     justify-content: space-between;
}
.header__wrapper__left{
    display: flex;
    gap: 30px;
}
.header__wrapper__right{
    display: flex;
    gap: 40px;
}
.wrapper__right__options{
    display: flex;
    gap: 15px;
}

.title{
    font-weight: 800;
    font-size: 24px;
    font-family: 'Poppins', 'Sans-serif';
    position: relative;
    top: -2px;
}
.wrapper__right__search{
    position: relative;
    top: -5px;
}
.wrapper__right__navbar{
        position: relative;
        top: 3px;
}
.options__img{
    position: relative;
    top: -12px;
}
</style>