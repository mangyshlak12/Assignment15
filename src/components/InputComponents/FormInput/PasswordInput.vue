<template>
    <div class="input" @click="click()">
        <div :class="{'label':isClicked}"><label for="" >Password</label></div>
        <input :class="{ 'inputText': isClicked, 'hidden': !isClicked }" type="password" v-model="inData">
    </div>    
</template>
<script>
    export default{
        data(){
            return{
                isClicked: false,
                inData: ''
            }
        },
        methods:{
            click(){
                if(!this.isClicked){
                    this.isClicked = true;
                }
            },
             handleClickOutside(event) {
                console.log(event.target.className);
                  if (event.target.className !== 'input' && event.target.className !== 'inputText' && event.target.className !== 'label'){
                    if(this.inData === ''){
                        this.isClicked = false;
                    }
                  }
             }
        },
         mounted() {
             document.addEventListener('click', this.handleClickOutside);
         }
    }
</script>
<style scoped>
.input{
    border-bottom: 1px solid black;
    width: 200px;
    padding: 5px;
    margin-bottom: 10px;
}
.hidden{
      opacity: 0;
      max-height: 0;
      display: none;
     
}
.label{
    font-size: 12px;
}
.inputText{
    opacity: 1;
    max-height: 100px;
    border: none;
    outline: none;
    
}
</style>