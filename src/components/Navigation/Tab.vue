<template>
    <div id="container">
  <div class="tabs">
    <div v-for="(tab, index) in tabs" :key="index" @click="selectTab(index)" :class="{ 'tab': true, 'active': activeTab === index }">
      {{ tab.name }}
    </div>
  </div>

  <div class="tab-content">
    {{ tabs[activeTab].content }}
  </div>
</div>
</template>
<script>
export default {
    data(){
        return{
            activeTab: 0,
            tabs: [
        { name: 'Tab 1', content: 'Content for Tab 1' },
        { name: 'Tab 2', content: 'Content for Tab 2' },
        { name: 'Tab 3', content: 'Content for Tab 3' },
      ]
        }
    },
    methods:{
        selectTab(index){
            this.activeTab = index;
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

    .tabs {
      display: flex;
      cursor: pointer;
    }

    .tab {
      padding: 10px 15px;
      background-color: #f2f2f2;
      border: 1px solid #ccc;
      border-bottom: none;
      border-radius: 5px 5px 0 0;
      margin-right: 5px;
    }

    .tab.active {
      background-color: #fff;
      border-bottom: 1px solid #ccc;
    }

    .tab-content {
      padding: 15px;
      border: 1px solid #ccc;
      border-radius: 0 0 5px 5px;
    }
</style>