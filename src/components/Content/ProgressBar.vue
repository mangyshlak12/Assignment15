<template>
  <div>
    <div class="progress-container">
      <div class="progress-bar" :style="{ width: progress + '%' }"></div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      progress: 56,
    };
  },
  methods: {
    increaseProgress() {
      if (this.progress < 100) {
        this.progress += 10;
      }
    },
  },
};
</script>

<style scoped>
.progress-container {
  width: 85%;
  height: 6px;
  border: 1px solid #ddd;
  border-radius: 6px;
  background: #d9e1cc;
}

.progress-bar {
  height: 100%;
  background-color: yellow; 
}
</style>
