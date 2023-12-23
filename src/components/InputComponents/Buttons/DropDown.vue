<template>
    
    <div class="container">
        <div class="dropdown">
        <div  @click="isClicked()" :class="{'select-clicked': isClick, 'select': !isClick}">
            <span class="selected">{{selectedItem}}</span>
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
                title: 'Framer'
             },
             {
                isSelect:false,
                title: 'Sketch'
             },
             {
                isSelect:false,
                title: 'Invision Studio'
             },
             {
                isSelect:false,
                title: 'Figma'
             },
             {
                isSelect:false,
                title: 'Adobe XD'
             }  
             ],
             selectedItem: 'Figma'  
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
            this.selectedItem = this.items[index].title;
            
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
    min-width: 15em;
    position: relative;
    margin: 2em;
}
.select{ 
    background: #2a2f3b;
    color: #fff;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1em;
    border: 2px #2a2f3b solid;
    border-radius: 0.5em;
    cursor: pointer;
    transition: background 0.3s;
}
.select-clicked{
    background: #2a2f3b;
    color: #fff;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1em;
    border: 2px #2a2f3b solid;
    border-radius: 0.5em;
    cursor: pointer;
    transition: background 0.3s;
    border: 2px #26489a solid;
    box-shadow: 0 0 0.8em #26489a;

}
.select:hover{
    background: #323741;

}
.caret{
    width: 0;
    height: 0;
    border-left: 5px solid transparent;
    border-right: 5px solid transparent;
    border-top: 6px solid #fff;
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
    background: #323741;
    border: 1px solid #363a43;
    border-radius: 0.5em;
    color: #9fa5b5;
    position: absolute;
    top: 3em;
    left: 50%;
    width:100% ;
    transform: translateX(-50%);
    opacity: 0;
    display: none;
    transition: 0.2s;
    z-index: 1;
}
.menu.menu-open li{
    padding: 0.7em 0.5em;
    margin: 0.3em 0;
    border-radius: 0.5em;
    border-radius: 0.5em;
    cursor: pointer;
}
.menu.menu-open li:hover{
    background: #2a2d35;
}
.active{
    background: #23242a;
}
.menu-open{
     list-style: none;
    padding: 0.2em 0.5em;
    background: #323741;
    border: 1px solid #363a43;
    border-radius: 0.5em;
    color: #9fa5b5;
    position: absolute;
    top: 3em;
    left: 50%;
    width:100% ;
    transform: translateX(-50%);
    transition: 0.2s;
    z-index: 1;
    display: block;
    opacity: 1;
}
</style>