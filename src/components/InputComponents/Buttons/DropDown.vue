<template>
    
    <div class="container">
        <div class="dropdown">
        <div  @click="isClicked()" :class="{'select-clicked': isClick, 'select': !isClick}">
            <span class="selected">{{selected}}</span>
            <div :class="{'caret-rotate': isClick, 'caret': !isClick}"></div>
        </div>
        <ul :class="{'menu-open': isClick, 'menu': !isClick}">
            <li v-for="(item,index) in items" :key="index" @click="isSelected(index)" :class="{'active': item.isSelect}">{{item.title}}</li>
        </ul>
        </div>    
    </div>
    
</template>
<script>
export default {
    data(){
        return{
             isClick:false,
             isSelect: false,
             items: [{
                isSelect:false,
                title: 'EN'
             },
             {
                isSelect:false,
                title: 'KAZ'
             },
             {
                isSelect:false,
                title: 'RUS'
             },
            
             ],
              selected: this.selectedItem
          
        }
    },
    methods:{
        isClicked(){
            this.isClick = !this.isClick;
        },
        isSelected(index){
            this.items.map(item=>{
                item.isSelect = false;
            });
            this.items[index].isSelect = true;
             this.selected = this.items[index].title;
            
        }
    },
    props:{
        selectedItem:{
            type:String,
            required: true
        }
    }
}
</script>
<style scoped>
*{
    box-sizing: border-box;
   
}
.container{
    display: flex;
    justify-content: center;
    align-items: center;
}
.dropdown{
    position: relative;
    
}
.select{ 
    background: rgb(126, 38, 197);
    color: #fff;
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 10px;
    font-size: 11px;
    position: relative;
    top: -6px;
    padding: 11px 13px;
    border: 1px #2a2f3b solid;
    border-radius: 30px;
    cursor: pointer;
    transition: background 0.3s;
}
.select-clicked{
   background: rgb(126, 38, 197);
    color: #fff;
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 10px;
    font-size: 11px;
    position: relative;
    top: -6px;
    padding: 11px 13px;
    border: 1px #2a2f3b solid;
    border-radius: 30px;
    cursor: pointer;
    transition: background 0.3s;

}

.caret{
    width: 0;
    height: 0;
    border-left: 3px solid transparent;
    border-right: 3px solid transparent;
    border-top: 4px solid #fff;
    transition: 0.3s;
}
.caret-rotate{
     width: 0;
    height: 0;
    border-left: 5px solid transparent;
    border-right: 5px solid transparent;
    border-top: 6px solid #fff;
    transition: 0.3s;
    transform: rotate(180deg);
}
.menu{
    list-style: none;
    padding: 0.2em 0.5em;   
     background: rgb(126, 38, 197);
    border: 1px solid #363a43;
    border-radius: 0.5em;
    color: #9fa5b5;
    position: absolute;
    left: 50%;
    width:100% ;
    transform: translateX(-50%);
    opacity: 0;
    display: none;
    transition: 0.2s;
    z-index: 1;
}
.menu.menu-open li{
    cursor: pointer;
}
.menu.menu-open li:hover{
    
    opacity: 0.5;
}
.active{
    opacity: 0.5;
}
.menu-open{
     list-style: none;
    padding: 0.2em 0.5em;
    background: rgb(126, 38, 197);
    border-radius: 0.5em;
    color: white;
    position: absolute;
    left: 50%;
    width:100% ;
    transform: translateX(-50%);
    transition: 0.2s;
    z-index: 1;
    display: block;
    opacity: 1;
}
</style>