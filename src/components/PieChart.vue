<template>
  <div ref="chart"></div>
</template>

<script>
import ApexCharts from 'apexcharts';
import 'apexcharts/dist/apexcharts.css';

export default {
  data() {
    return {
      chartOptions: {
        chart: {
          type: 'donut',
        },
        labels: ['Primary', 'Promotion', 'Forum', 'Socials', 'Spam'],
      },
      chartSeries: [27, 11, 22,15,25],
      
        
    };
  },
  mounted() {
    this.renderChart();
  },
  methods: {
    renderChart() {
      const options = {
        chart:  this.chartOptions.chart,
        labels: this.chartOptions.labels,
        series: this.chartSeries,
      };

      const chart = new ApexCharts(this.$refs.chart, options);
      chart.render();
    },
  },
  watch: {
    chartOptions: {
      handler() {
        this.renderChart();
      },
      deep: true,
    },
    chartSeries() {
      this.renderChart();
    },
  },
};
</script>

<style scoped>
    
</style>