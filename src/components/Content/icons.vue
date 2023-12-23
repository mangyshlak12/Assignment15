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
</style>