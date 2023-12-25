<template>
  <div class="container">
    <button v-if="link!=''"  @mouseover="showTooltip" @mouseout="hideTooltip" class="button">
      <div class="container__wrapper"> 
          <GraphItem class="elem" v-for="(element, index) in styles"  
                        :key="index"  
                        :title="element.elementName"  
                        :color1="element.color1" 
                        :color2="element.color2" 
                        :height1="element.height1" 
                        :height2="element.height2" 
                        > 
          </GraphItem>
      </div>
      </button>
                  
    <div v-if="isTooltipVisible" class="tooltip">
      {{ tooltipText }}
      <br>
      <span>{{date}}</span>
    </div>
  </div>
</template>

<script>
import GraphItem from '../GraphItem.vue';
import Icons from './icons.vue';

export default {
  data() {
    return {
      isTooltipVisible: false,
      styles: [ 
                    {elementName: 'Jan', color1: '#ef6d4d', height1: '65%' , color2:'rgba(241,199,103,255)' , height2: '80%'}, 
                    {elementName: 'Feb', color1: '#ef6d4d', height1: '50%' , color2:'rgba(241,199,103,255)' , height2: '45%'}, 
                    {elementName: 'Mar', color1: '#ef6d4d', height1: '40%' , color2:'rgba(241,199,103,255)' , height2: '45%'}, 
                    {elementName: 'Apr', color1: '#ef6d4d', height1: '47%' , color2:'rgba(241,199,103,255)' , height2: '49%'}, 
                    {elementName: 'May', color1: '#ef6d4d', height1: '55%' , color2:'rgba(241,199,103,255)' , height2: '60%'}, 
                    {elementName: 'Jun', color1: '#ef6d4d', height1: '70%' , color2:'rgba(241,199,103,255)' , height2: '60%'}, 
                    {elementName: 'Jul', color1: '#ef6d4d', height1: '85%' , color2:'rgba(241,199,103,255)' , height2: '80%'}, 
                    {elementName: 'Aug', color1: '#ef6d4d', height1: '40%' , color2:'rgba(241,199,103,255)' , height2: '43%'}, 
                    {elementName: 'Sep', color1: '#ef6d4d', height1: '42%' , color2:'rgba(241,199,103,255)' , height2: '37%'}, 
                    {elementName: 'Oct', color1: '#ef6d4d', height1: '25%' , color2:'rgba(241,199,103,255)' , height2: '27%'}, 
                    {elementName: 'Nov', color1: '#ef6d4d', height1: '70%' , color2:'rgba(241,199,103,255)' , height2: '72%'}, 
                    {elementName: 'Dec', color1: '#ef6d4d', height1: '61%' , color2:'rgba(241,199,103,255)' , height2: '70%'}, 
                ] ,
    
    }
  },
  methods: {
    showTooltip() {
      this.isTooltipVisible = true;
    },
    hideTooltip() {
      this.isTooltipVisible = false;
    }
  },
  props:{
      link:{
        type: String,
        required: true
      },
      tooltipText:{
        type: String,
        required: true
      },
      date:{
        type:String,
        required: true
      }
  },
  components:{
    Icons,
    GraphItem
  }
} 
</script>

<style scoped>
.tooltip {
  position: absolute;
  bottom: -25px;
  left: 400px;
  background-color: white;
  border: 1px solid #d9e1cc;
  color: #96A0AF ;
  font-size: 18xp;
  padding: 10px 10px;
  border-radius: 5px;
  
}
.button{
  border: none;
}
.container{
  margin-top: 20px;
  width: 100% ;
}
.container__wrapper{
  display: flex;
  height: 200px;
  width: 480px  ;
}
</style>