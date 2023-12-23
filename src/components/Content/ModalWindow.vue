<template>
    <div v-if="isVisible" class="window" @click="hideBox()"></div>
    <div class="container">
        <button @click="showBox()">Press</button>
        <div :class="{'active': isVisible, 'box': !isVisible}">
            <div class="content">
                <p>{{message}}</p>
                <span class="close_button" @click="hideBox">Close</span>
            </div>
        </div>
        </div>    
</template>
<script>
export default {
    data(){
        return{
            message: 'Bul gajaiyp alemnin oleni toktamaidy',
            isVisible: false
        }
    },
    methods:{
        showBox(){
            this.isVisible = true;
        },
        hideBox(){
            this.isVisible = false;
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
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
}
.box{
    width: 400px;
    position: absolute;
    transform: scale(0.1);
    visibility: hidden;
    transition: 0.5s;
}
.active{
    position: absolute;
    transform: scale(1.0);
    visibility: visible;
    transition: 0.5s;
}
.content p{
    display: flex;
    align-items: center;
    justify-content: center;
}
.content span{
    display: flex;
    justify-content: center;
    align-items: center;
}
.window{
    width: 100%;
    height: 100vh;
    position: fixed;
    background: red;
    opacity: 0.1;
}
</style>