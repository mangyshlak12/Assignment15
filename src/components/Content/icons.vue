 <template>
   <img :src= 'link'  alt="" :class="name">
 </template>
 <script>
export default {
 props:{
        link:{
                type: String,
                required: true
              },
         name:{
                type:String,
                required: true
         }
        }
  }
</script> 
<style scoped>
.hola{
    width: 45px;
}
.avatar{
    width: 45px;
}
.firstb{
  width: 162.5px;
  border-radius: 50%;
}
.prbar{
  width: 46px;
}
.linechart{
  width: 460px;
  height: 200px; 
}
.avatarr{
  width: 33px;
}
.rotate{
  transform: rotate(90deg);
}
.avatarrr{
  width: 29px;
  background: rgb(87, 35, 155);
  border-radius: 50%;
}
</style>