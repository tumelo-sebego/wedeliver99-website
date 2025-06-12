<template>
  <div class="dashboard-container">
    <Menu />
    <div class="dashboard-content">
      <h1>Dashboard</h1>
      <!-- Dashboard content will go here -->
    </div>
  </div>
</template>

<script>
import Menu from '../components/Menu.vue'

export default {
  name: 'Dashboard',
  components: {
    Menu
  }
}
</script>

<style scoped>
.dashboard-container {
  display: flex;
}

.dashboard-content {
  flex: 1;
  margin-left: 250px;
  padding: 20px;
}

@media (max-width: 768px) {
  .dashboard-content {
    margin-left: 0;
    padding-top: 60px;
  }
}
</style>