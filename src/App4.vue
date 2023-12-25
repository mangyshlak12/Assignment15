<template>
    <div class="container">
        <LeftSide :pages="pages">
            <div class="right__container">
                <Header/>
            </div>
    </div>
</template>
<script>
import Header from './components/Content/header.vue';
import LeftSide from './components/LeftSide.vue';


export default {
components:{
    LeftSide,
    Header
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
    display: flex;
}
</style>