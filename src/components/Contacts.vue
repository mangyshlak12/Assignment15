<template>
        <div class="conten">
            <div class="header">
                <Icons :link="Dots"/>
            </div>
            <div class="content__body">
                <div> <Icon :link="dat.src" name="data"/></div>
                <div>{{dat.name}}</div>
                <div>{{dat.job}}</div>
                <div class="contacts">
                    <Icons :link="Contact"/>
                    <Icons :link="message"/>
                    <Icons :link="video"/>
                </div>
            </div>
        </div>
</template>
<script>
import Icons from './Content/icons.vue'
import Dots from '../Assets/3dots.svg'
import Contact from '../Assets/contact.svg'
import message from '../Assets/message.svg'
import video from '../Assets/video.svg'
import Avatar from '../Assets/UA8.png'
export default {
    components:{
        Icons,
        
    },
    data(){
        return{
            Dots,
            Contact,
            message,
            video,
             dat:{
                src: Avatar,
                 name: 'Jakob Gouse',
                 job: 'Recblue Studios'
          }
        }
    },
    
}
</script>
<style scoped>
.conten{
    width: 400px;
    padding: 20px 40px;
}
</style>