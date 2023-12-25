<template>
    <div :class="{ 'active': isOn, 'toggle': !isOn }" @click="changeToggle()" >
        <i class="indicator"></i>
    </div>
</template>
<script>
export default {
    data(){
        return{
            isOn: false
        }
    },
    methods:{
        changeToggle(){
            this.isOn = !this.isOn;
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
.toggle{
    position: relative;
    display: block;
    width: 40px;
    height: 20px;
    border-radius: 50px;
    background: #d9e1cc;
    transition: 0.5s;
    cursor: pointer;
}
.indicator{
    position: absolute;
    width: 20px;
    height: 20px;
    left: 0;
    top: 0  ;
    background: gray;
    border-radius: 50%;
    transform: scale(0.9);
    opacity: 0.9;
    transition: 0.5s;

}
.active{
    position: relative;
    display: block;
    width: 40px;
    height: 20px;
    border-radius: 20px;
    background: #222;
    transition: 0.5s;
    cursor: pointer;
    background-color: #d9e1cc;
}
.active .indicator{
    background: rgb(127, 59, 206);
    left: 20px;
    transition: 0.5s;
}


</style>