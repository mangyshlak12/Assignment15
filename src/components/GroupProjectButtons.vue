<template>
        <ul>
            <li v-for="(item,index) in buttons" :key="index" @click="press(index)">{{item.title}}</li>
        </ul>
        <div class="content" v-for="(item,index) in filterArray()" :key="index" :style="{position: absolute, top: (210 + (index*120)) + 'px'}">
            <div class="left">
                    <div class="hash">#P-000441425</div>
                    <div class="title">{{item.title}}</div>
                    <div class="data">Created on Sep 8th, 2020</div>
            </div>
            <div class="center">
                <div class="center__content" v-for="(item,index) in data" :key="index">
                    <div>
                        <Icons :link="item.src" name="avatarrr"/>
                    </div>
                    <div>
                        <span class="job">{{item.job}}</span>
                        <br>
                        <span class="name">{{item.name}}</span>
                    </div>
                </div>
            </div>
            <div class="right">
               <div class="r__button">
                <Button :name="item.display" clas="display" :col="item.color"/>
                </div> 
            </div>
            <div>

            </div>
        </div>
</template>
<script>
import Avatar from '../Assets/UA8.png';
import Light from '../Assets/lighting.svg';
import Icons from './Content/icons.vue';
import Button from './InputComponents/Buttons/Button.vue';

export default {
    data(){
        return{
            buttons:[
                {
                    title: 'All status',
                    isSelected: false
                },
                  {
                    title: 'On Progress',
                    isSelected: false
                },
                  {
                    title: 'Pending',
                    isSelected: false
                },
                  {
                    title: 'Closed',
                    isSelected: false
                }
            ],
            selectedOption: 'All status',
            data: [
                {
                    src: Avatar,
                    job: 'Client',
                    name: 'James Jr.'
                },
                 {
                    src: Avatar,
                    job: 'Client',
                    name: 'James Jr.'
                },
                 {
                    src: Light,
                    job: 'Client',
                    name: 'James Jr.'
                }

            ]
        }
    },
    props:{
        project:{
            type: Object,
            required: true
        }
    },
    components:{
        Icons,
        Button
    },
    methods:{
        press(index){
            console.log(this.buttons[index].title);
            if(this.buttons[index].title === 'All status'){
              this.selectedOption = 'All status';
                return this.project;
            }
            this.buttons.map(item=>{
                item.isSelected = false;
            });
            this.buttons[index].isSelected = true;
            
            this.selectedOption = this.buttons[index].title.toLocaleUpperCase();
            
          

        },
        filterArray(){
            if(this.selectedOption === 'All status'){
                 console.log(this.project);
                return this.project;
            }
            return this.project.filter((item) => item.display === this.selectedOption);
        }
    }
}
</script>
<style scoped>
ul{
    list-style: none;
    display: flex;
    gap: 40px;
}
.content{
    position: absolute;
    top: 210px;
    display: flex;
    justify-content: space-between;
    width: 75%;
    background: white;
    padding: 20px;
    border-radius: 20px;
}
.center{
    display: flex;
    gap: 80px;
   width: 500px;
    justify-content: center;
}
.center__content{
    display: flex;
    gap: 15px;
    align-items: center;
}
.active{
    display: none;
}
.right{
    width: 130px;   
}
.r__button{
    display: flex;
    justify-content: center ;
    align-items: center;
    position: relative;
    top: 5px;
}
.hash{
    color: gray;
    font-size: 14px;
}
.title{
    margin-top:5px ;
    font-weight: 600;
}
.data{
    color: gray;
    font-size: 12px;
    margin-top: 10px ;
    font-weight: 600;
}
.job{
    font-size: 12px;
    color: gray;
}
.name{
    font-weight: 500;
    font-size: 18px;
}
</style>