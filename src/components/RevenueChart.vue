<template>
    <div class="chart-container">
      <line-chart :chart-data="chartData" :options="chartOptions" />
    </div>
  </template>
  
  <script lang="ts">
  import { defineComponent } from 'vue';
  import { Line } from 'vue-chartjs';
  import {
    Chart as ChartJS,
    Title,
    Tooltip,
    Legend,
    LineElement,
    CategoryScale,
    LinearScale,
    PointElement,
    Filler,
  } from 'chart.js';
  
  ChartJS.register(Title, Tooltip, Legend, LineElement, CategoryScale, LinearScale, PointElement, Filler);
  
  export default defineComponent({
    name: 'RevenueChart',
    components: {
      'line-chart': Line,
    },
    setup() {
      const chartData = {
        labels: ['January', 'February', 'March', 'April', 'May', 'June', 'July'],
        datasets: [
          {
            label: 'Revenue',
            data: [6000, 8000, 7500, 9000, 10000, 8500, 9500],  // Rastgele veriler
            borderColor: '#3498db',
            backgroundColor: 'rgba(52, 152, 219, 0.2)',
            fill: true,
          },
        ],
      };
  
      const chartOptions = {
        responsive: true,
        maintainAspectRatio: false,
        plugins: {
          legend: {
            display: true,
          },
        },
        scales: {
          x: {
            display: true,
          },
          y: {
            display: true,
            beginAtZero: true,
          },
        },
      };
  
      return {
        chartData,
        chartOptions,
      };
    },
  });
  </script>
  
  <style scoped>
  .chart-container {
    width: 100%;
    height: 300px;
  }
  </style>