  <template>
  <div class="container">
        <LeftSide :pages="pages"/>

    <div class="right__container">
          <Header/>
          <div class="body">
              <div class="left__body">
                  <div class="left__body__first">
                      <div class="body__first__left">
                          <div class="first__title">Manage your project in one touch</div>
                          <div class="first__text">Let Fillow manage your project automatically with our best AI systems</div>
                          <div class="first__button"><Button name="Try Free Now" clas="fButton"/></div>
                      </div>
                      <div class="body__first__right">
                          <div><Icons :link="FirstB" name="firstb"/></div>
                      </div>
                  </div>

                  <div class="left__body__second">
                      <div class="second__header">
                        <div class="second__header__title">Project Statistics</div>
                        <div class="second__header__option">
                          <div><GroupButtons :options="options"/></div>
                          <div class="dot"><Icons :link="Dots"/></div>
                          </div>
                      </div>
                      <div class="second__body">
                        <div class="second__statistic">
                            <div class="second__statistic__total">
                                <div>
                                  <Icons :link="PrBar" name="prbar"/>
                                </div>
                                <div><span class="prbar__total">246</span>
                                <br>
                                <span class="prbar__total__content">Total Projects</span>
                                </div>
                            </div>
                            <div class="second__statistic__fragment">
                                  <div class="fragment__fpart">
                                      <span class="fpart__total">167</span>
                                    <br>
                                    <span class="part__message">On Going</span>
                                  </div>
                                  <div class="fragment__spart">
                                      <span class="spart__total">28</span>
                                    <br>
                                    <span class="part__message">Unfinished</span>
                                  </div>
                            </div>
                        </div>

                        <div>
                            <Tooltip :link="Chart" tooltipText="56 Project" date="Oct 24th, 2020"/>
                        </div>
                        <div class="second__body__last">
                            <div class="second__last__wrapper">
                              <span>Number</span>
                              <ToggleSwitch/>
                            </div>
                            <div class="second__last__wrapper">
                              <span>Analytics</span>
                              <ToggleSwitch/>
                            </div>
                        </div>

                      </div>
                      </div>

                      <div class="left__body__third">
                        <div class="third__header">
                          <div class="third__header__title">
                            Completion Project Rate
                          </div>
                          <div><Icons :link="Dots"/></div>
                        </div>
                        <div class="third__body">
                            <!-- <Icons :link="LineChart" name="linechart" /> -->
                            <LineChart />
                        </div>
                      </div>

                      <div class="left__body__forth">
                        <div class="forth__header">
                          <div class="forth__header__left">
                            <span class="forth__header__title">Recent Emails</span>
                            <br>
                            <span class="forth__header__content">Lorem ipsum dolor sit amat</span>  
                          </div>
                          <div class="forth__header__right">
                                  <Button name="View More" class="view"/>
                          </div>
                        </div>
                        <div class="forth__body">
                            <div class="forth__body__container">
                                <Card v-for="(card, index) in cards" :key="index" :src="card.src" :question="card.question" :content="card.content" :isSelected="card.isSelected" />
                            </div>
                        </div>
                  
                      </div>
                
                  </div>
                  <div class="right__body">
                      <div class="header">
                        <NewCard v-for="(item,index) in newCard" :key="index" :item="item" :name='index'/>
                      </div> 
                      <div class="right__first">
                        <div class="right__left__first">
                          <div class="right__title">Fillow Company Profile Website Project</div>
                          <div class="right__content">Lorem ipsum dolor sit amet consectetur adipisicing elit. Nostrum perspiciatis exercitationem fugit magnam quos nihil.</div>
                        </div>
                        <div class="right">
                            <img :src="ProgressB" alt="">
                        </div>
                      </div>

                      <div class="right__second">
                          <div class="second__left">
                              <div class="right__title">Email Categories</div>
                              <div class="right__content">Lorem ipsum dolor sit amet</div>
                              <div class="piechart">
                                  <PieChart/>
                              </div>
                          </div>    
                      </div>
                      <div class="right__third">
                          <div class="third__header">
                              <div class="header__third__left">
                                <span class="right__title">Messages</span>
                                  <br>
                                <div class="right__text">Lorem ipsum dolor sit amet</div>
                              </div>
                              <div class="header__third__right">
                                  <Button name="+New Messages" clas="newmessage"/>
                              </div>
                          </div>
                          <div class="third__body__r">
                            <FooterCard v-for="(item,index) in footercards" :key="index" :item="item"/>
                          </div>
                      
                      </div>
                                    
              </div>
              </div>
          </div>
      </div>
  
      
</template>

<script>
      import ProgressB from './Assets/ProgressB.jpg';
      import Icons from './components/Content/icons.vue'
      import TextType from './components/Others/TextType.vue';
      import NavigationLinks from './components/Navigation/NavigationLinks.vue';
      import ProgressBar from './components/Content/ProgressBar.vue';
      import Header from './components/Content/header.vue'
      import facebookImage from './Assets/facebook.png';
      import Homeimage from './Assets/home.svg';
      import lighting from './Assets/lighting.svg';
      import contact from './Assets/contact.svg';
      import canvan from './Assets/canvan.svg'
      import Analytics from './Assets/Analytics.svg'
      import Calendar from './Assets/calendar.svg';
      import Message from './Assets/message.svg';
      import Avatar from './Assets/UA8.png';
      import Star from './Assets/star.svg';
      import GroupButtons from './components/InputComponents/GroupButtons.vue';
      import FirstB from './Assets/body__first.jpg';
      import Button from './components/InputComponents/Buttons/Button.vue';
      import Dots from './Assets/3dots.svg';
      import PrBar from './Assets/UA6.png';
      import Chart from './Assets/chart.svg';
      import LineChartt from './Assets/linechart.png'
      import ToggleSwitch from './components/InputComponents/ToggleSwitch.vue';
      import Tooltip from './components/Content/Tooltip.vue';
      import Card from './components/Containers/Card.vue';
      import Cardfirst from './components/Containers/Cardfirst.vue';
      
      import LinesVertical from './Assets/LinesVertical.svg';
      import LeftSide from './components/LeftSide.vue';
      import LineChart from './components/LineChart.vue';
      import NewCard from './components/NewCard.vue';
      import PieChart from './components/PieChart.vue';
import FooterCard from './components/FooterCard.vue';
     
    export default{
      components:{
        Icons,
        TextType,
        NavigationLinks,
        ProgressBar,
        Header,
        GroupButtons,
        Button,
        ToggleSwitch,
        Tooltip,
        Card,
        Cardfirst,
        LeftSide,
        LineChart,
        NewCard,
        PieChart,
        Button,
        FooterCard
      },
      data(){
        return{
          ProgressB,
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
          FirstB,
          LinesVertical,
          options:[
            {
                isSelected: false,
                option: 'Monthly'
            },
            {
                isSelected: false,
                option: 'Weekly'
            },
            {
                isSelected: true,
                option: 'Daily'
            }
          ],
          Dots,
          PrBar,
          Chart,
          LineChartt,
          cards: [
              {
                src: Avatar,
                question: 'How to improve project management flows',
                content: 'Lorem ipsum dolor sit amet consectetur',
                isSelected: true
              },
               {
                src: Avatar,
                question: 'Project Plan Management for Kleen Studios',
                content: 'Lorem ipsum dolor sit amet consectetur',
                isSelected: false
              },
               {
                src: Avatar,
                question: 'Fillow Final UseCase Diagram',
                content: 'Lorem ipsum dolor sit amet consectetur',
                isSelected: false
              },
               {
                src: Avatar,
                question: 'Weekly Design Inspirations by Envato',
                content: 'Lorem ipsum dolor sit amet consectetur',
                isSelected: false
              },
            
          ],
          pages:[
            {
              name: 'index.html',
              isSelected: true
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
              isSelected: false
            },
            {
              name: 'index4.html',
              isSelected: false
            }

          ]
          ,
          newCard: [
            {
              title: 'Total Clients',
              number: 68,
              percent: '+0.5%',
              src: LineChart
            },
              {
              title: 'Total Clients',
              number: 68,
              percent: '+0.5%',
              src: ''
            },
              {
              title: 'Total Clients',
              number: 68,
              percent: '+0.5%',
              src: LineChart
            },
              {
              title: 'Total Clients',
              number: 68,
              percent: '+0.5%',
              src: LineChart
            }

          ],
          footercards: [
            {
              src: Avatar,
              name: 'Maren Rosser',
              message: 'Hei, dont forget to clear server cache!',
              lateseen: '1min ago'
            },
             {
              src: Avatar,
              name: 'Kaiya Bergson',
              message: 'Remember that project due is tomorrow',
              lateseen: '25min ago'
            },
             {
              src: Avatar,
              name: 'Cristofer Troff',
              message: 'Maybe we should schedule that meeting',
              lateseen: '43min ago'
            },
             {
              src: Avatar,
              name: 'Ruben Press',
              message: 'Ok sir.I will fix it as soon as possible',
              lateseen: 'Yesterday, 8:24 AM'
            },
             {
              src: Avatar,
              name: 'Ann Rosser',
              message: 'I dont know where that files saved dude',
              lateseen: 'December 12th, 2020 00:24 AM'
            },
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
.right__container{
  width: 81%; 
  
}
.body{
  background-color: #f3f0f9 ;
  padding: 30px 30px 0px;
  height: 100%;
  display: flex;
  gap: 25px;
}
.left__body__first{
  display: flex;
  background-color: rgb(136, 97, 180);
  border-radius: 10px;
  padding: 30px;
  width: 100%;
}
.left__body{
  width: 60% ;
}
.body__first__right{
   position: relative;
  top: 35px;
  right: 20px;
  
} 
.first__title{
  font-weight: bold;
  color: white;
  font-size: 30px;
  width: 95%;
}
.first__text{
  width: 72%;
  color: white;
  font-weight: 500;
  margin-top: 15px;
}
.first__button{
margin-top: 30px;
}
.left__body__second{
  background-color: white;
  border-radius: 15px;
  width: 100%;
  margin: 25px 0px ;
  padding: 20px;
}
.second__header{
  display: flex;
  justify-content: space-between;
}
.second__header__title{
  font-size: 20px;
  font-weight: 600;
}
.second__header__option{
  display: flex;
  gap: 5px;
}
.dot{
  position: relative;
  top: 7px;
}
.second__body{
  margin-top: 20px;
}
.second__statistic{
  display: flex;
  justify-content: space-between;
}
.second__statistic__total{
  display: flex;
  align-items: center;
  gap: 16px;
}
.prbar__total{
  position: relative;
  top: -4px;
  font-weight: 700;
  font-size: 20px;
}
.prbar__total__content{
  font-size: 13px;
}
.second__statistic__fragment{
  display: flex;
  gap: 50px;
  font-size: 20px;
}
.fpart__total::before{
    content: '';
    padding: 0px 11px;
     position: relative;
    right: 10px;
    
    border-radius: 50%;
    background: goldenrod;
}
.spart__total::before{
    content: '';
    position: relative;
    right: 10px;
    padding: 0px 11px;
    border-radius: 50%;
    background: pink;
}
.spart__total{
  font-weight: bold;
  position: relative;
  right:20px;
}
.fpart__total{
  font-weight: bold;
  position: relative;
  right:20px;
}
.part__message{
  font-size: 14px;
}
.second__body__last{
  display: flex;
  gap: 30px;
  margin: 25px 0px 0px 0px;
}
.second__last__wrapper{
  display: flex;
  gap: 15px;
}
.left__body__third{
  background: white ;
  width: 100%;
  padding: 20px;
  border-radius: 15px;
}
.third__header{
  display: flex;
  justify-content: space-between;
}
.third__header__title{
  font-weight: 700;
  font-size: 18px;
}
.third__body{
  margin: 30px 0px 0px 0px;
}
.left__body__forth{
  padding: 25px;
  background: white;
  width: 100%;
  border-radius: 15px;
  margin: 25px 0px;
}
.forth__header{
  display: flex;
justify-content: space-between;
align-items: center;
}
.forth__body{
  
    margin-top: 35px;
}
.forth__header__title{
  font-weight: bold;
  font-size: 18px;
}
.forth__header__content{
  font-size: 14px;
  color: #96A0AF ;
}
.right__body{
  width: 100%;
 
}
.header{
  display: flex;
  gap: 25px;
  flex-wrap: wrap;
}
.right__first{
  display: flex;
   border-radius: 10px;
  margin-top: 27px ;
  background: white;
  padding: 30px;
  gap: 15px;
}
.right__title{
  font-weight: 700;
  font-size: 20px;
}
.right__content{
  margin-top: 15px ;
  font-size: 14px;

}
.right img{
  width: 210px;
  height: 180px;
}
.right__second{
  background: white;
  margin-top: 30px;
  border-radius: 10px;
  padding: 25px;
}
.header__third__left .right__text{
  margin-top: 5px ;
}
.right__third{
  margin-top: 30px;
  background: white;
  border-radius: 10px;
  padding: 20px;
}
.right__text{

}
</style>
