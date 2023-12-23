<template>
        <div v-if="isMessageBoxVisible" class="window" @click="hideMessageBox"></div>
  <div>
    <button @click="showMessageBox">Alert</button>
    <div v-if="isMessageBoxVisible" class="message-box">
      <div class="message-content">
        <p>{{ message }}</p>
        <span @click="hideMessageBox" class="close-button">Close</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isMessageBoxVisible: false,
      message: "This is a message!",
    };
  },
  methods: {
    showMessageBox() {
      this.isMessageBoxVisible = true;
    },
    hideMessageBox() {
      this.isMessageBoxVisible = false;
    },
  },
};
</script>

<style scoped>
.message-box {
  position: fixed;
  top: 40%;
  left: 45%;
  background-color: #f1f1f1;
  padding: 20px;
  border: 1px solid #ccc;
}
.window{
    width: 100%;
    height: 100vh;
    background-color: red;
    opacity: 0.1;
    position: fixed;


    z-index: 1;
}
.message-content {
  position: relative;

}

.close-button {
  display: flex;
  justify-content: center;
  font-size: 18px;
  cursor: pointer;
}
</style>