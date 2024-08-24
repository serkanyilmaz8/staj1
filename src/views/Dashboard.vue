<template>
  <div class="dashboard-container">
    <Sidebar />
    <div class="main-content">
      <Header />
      <div class="dashboard-content">
        <div class="stats-cards">
          <div class="card">
            <div class="card-header">
              <h3>Users</h3>
              <p class="stat-number">4,523</p>
              <span class="stat-change positive">+16%</span>
            </div>
          </div>
          <div class="card">
            <div class="card-header">
              <h3>Views</h3>
              <p class="stat-number">2,523</p>
              <span class="stat-change positive">+11%</span>
            </div>
          </div>
          <div class="card">
            <div class="card-header">
              <h3>Conversion</h3>
              <p class="stat-number">9,832</p>
              <span class="stat-change negative">-1%</span>
            </div>
          </div>
          <div class="card">
            <div class="card-header">
              <h3>Revenue</h3>
              <p class="stat-number">$6,364</p>
              <span class="stat-change neutral">0%</span>
            </div>
          </div>
        </div>
        <div class="chart">
          <h3>Statistics</h3>
          <div class="simple-chart">
            <div class="bar" style="height: 50%;"></div>
            <div class="bar" style="height: 70%;"></div>
            <div class="bar" style="height: 60%;"></div>
            <div class="bar" style="height: 80%;"></div>
            <div class="bar" style="height: 90%;"></div>
            <div class="bar" style="height: 40%;"></div>
            <div class="bar" style="height: 30%;"></div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import Sidebar from '@/components/Sidebar.vue';
import Header from '@/components/Header.vue';

export default defineComponent({
  name: 'Dashboard',
  components: {
    Sidebar,
    Header,
  },
});
</script>

<style scoped>
.dashboard-container {
  display: flex;
}

.main-content {
  flex: 1;
  padding: 20px;
  background-color: #f5f5f5;
}

.dashboard-content {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.stats-cards {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 20px;
}

.card {
  padding: 20px;
  background-color: #ffffff;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  border-radius: 12px;
  position: relative;
  height: 180px;
}

.card-header {
  text-align: center;
}

.card h3 {
  font-size: 18px;
  color: #34495e;
}

.stat-number {
  font-size: 32px;
  font-weight: bold;
  margin: 10px 0;
}

.stat-change {
  display: inline-block;
  margin-top: 10px;
  font-size: 14px;
  font-weight: bold;
  padding: 4px 10px;
  border-radius: 20px;
}

.stat-change.positive {
  background-color: #2ecc71;
  color: white;
}

.stat-change.negative {
  background-color: #e74c3c;
  color: white;
}

.stat-change.neutral {
  background-color: #95a5a6;
  color: white;
}

.simple-chart {
  display: flex;
  align-items: flex-end;
  justify-content: space-around;
  height: 200px;
  background-color: #f9f9f9;
  padding: 20px;
  border-radius: 12px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.bar {
  width: 14%;
  background-color: #3498db;
  border-radius: 8px;
  transition: all 0.3s ease-in-out;
}

.bar:hover {
  background-color: #2980b9;
  transform: scaleY(1.1);
}
</style>