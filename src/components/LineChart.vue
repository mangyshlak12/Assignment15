<template>
  <div>
    <canvas ref="lineChart"></canvas>
  </div>
</template>

<script>
import Chart from 'chart.js/auto';

export default {
  data() {
    return {
      chartData: {
        labels: ['S', 'T', 'M', 'W', 'T', 'F', 'S'],
        datasets: [
          {
            // label: 'My Dataset',
            borderColor: 'rgba(75, 192, 192, 1)',
            data: [65, 59, 80, 81, 56,45,55],
            fill: false,
          },
        ],
      },
      chartOptions: {
        responsive: true,
        maintainAspectRatio: false,
        scales: {
          x: {
            type: 'category',
          },
          y: {
            beginAtZero: true,
          },
        },
      },
    };
  },
  mounted() {
    this.renderChart();
  },
  methods: {
    renderChart() {
      const ctx = this.$refs.lineChart.getContext('2d');
      new Chart(ctx, {
        type: 'line',
        data: this.chartData,
        options: this.chartOptions,
      });
    },
  },
};
</script>

<style scoped>
/* Add any additional styles for your component if needed */
</style>