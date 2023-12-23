<template>
    <div id="container">
  <button class="toggle-button" @click="toggleDrawer">Toggle Drawer</button>

  <div class="drawer" :class="{ 'open': isDrawerOpen }">
    <p>This is the content of the drawer. You can put any content here.</p>
  </div>
</div>

</template>
<script>
export default {
    data(){
        return{
            isDrawerOpen: false
        }
    },
    methods:{
        toggleDrawer(){
            this.isDrawerOpen = !this.isDrawerOpen;
        }
    }
}
</script>
<style scoped>
#container {
      font-family: Arial, sans-serif;
      width: 60%;
      margin: 20px auto;
    }

    .drawer {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      width: 250px;
      height: 100%;
      background-color: #f2f2f2;
      padding: 20px;
      box-shadow: 2px 0 5px rgba(0, 0, 0, 0.1);
    }

    .drawer.open {
      display: block;
    }

    .toggle-button {
      cursor: pointer;
      padding: 10px 15px;
      background-color: #333;
      color: #fff;
      border: none;
      border-radius: 5px;
    }
</style>