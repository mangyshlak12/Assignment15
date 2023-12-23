<template>
  <div>
    <button @mouseover="showTooltip" @mouseout="hideTooltip">Hover me</button>
    <div v-if="isTooltipVisible" class="tooltip">
      {{ tooltipText }}
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isTooltipVisible: false,
      tooltipText: "This is a tooltip!"
    }
  },
  methods: {
    showTooltip() {
      this.isTooltipVisible = true;
    },
    hideTooltip() {
      this.isTooltipVisible = false;
    }
  }
} 
</script>

<style scoped>
.tooltip {
  position: absolute;
  background-color: #333;
  color: #fff;
  padding: 5px;
  border-radius: 5px;
  
}
</style>