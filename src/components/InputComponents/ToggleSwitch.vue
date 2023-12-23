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
    width: 100px;
    height: 50px;
    border-radius: 50px;
    background: #222;
    transition: 0.5s;
    cursor: pointer;
}
.indicator{
    position: absolute;
    width: 50px;
    height: 50px;
    left: 0;
    top: 0  ;
    background: linear-gradient(to bottom, #444,#222);
    border-radius: 50%;
    transform: scale(0.9);
    opacity: 0.9;
    transition: 0.5s;

}
.active{
    position: relative;
    display: block;
    width: 100px;
    height: 50px;
    border-radius: 50px;
    background: #222;
    transition: 0.5s;
    cursor: pointer;
    background-color: #d9e1cc;
}
.active .indicator{
    left: 50px;
    transition: 0.5s;
}

</style>