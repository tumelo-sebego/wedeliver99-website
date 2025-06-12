<template>
  <div class="menu-container">
    <div class="logo">
      <img src="../assets/logo.png" alt="WeDeliver99 Logo" />
    </div>
    <div class="menu">
      <router-link to="/dashboard" class="menu-item">
        <span class="material-icons">dashboard</span>
        <span>Dashboard</span>
      </router-link>
      <router-link to="/clients" class="menu-item">
        <span class="material-icons">groups</span>
        <span>Clients</span>
      </router-link>
      <router-link to="/orders" class="menu-item">
        <span class="material-icons">shopping_cart</span>
        <span>Orders</span>
      </router-link>
      <router-link to="/drivers" class="menu-item">
        <span class="material-icons">local_shipping</span>
        <span>Drivers</span>
      </router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Menu'
}
</script>

<style scoped>
.menu-container {
  position: fixed;
  top: 0;
  left: 0;
  height: 100vh;
  width: 250px;
  background: #ffffff;
  box-shadow: 2px 0 10px rgba(0, 0, 0, 0.1);
  display: flex;
  flex-direction: column;
}

.logo {
  padding: 20px;
  text-align: center;
}

.logo img {
  max-width: 150px;
  height: auto;
}

.menu {
  display: flex;
  flex-direction: column;
  padding: 20px 0;
}

.menu-item {
  display: flex;
  align-items: center;
  padding: 15px 30px;
  text-decoration: none;
  color: #666;
  transition: all 0.3s ease;
}

.menu-item:hover {
  background-color: #f5f5f5;
}

.menu-item.router-link-active {
  color: #42b983;
  background-color: #f5f5f5;
  border-left: 4px solid #42b983;
}

.material-icons {
  font-size: 24px;
  margin-right: 15px;
}

.menu-item span:not(.material-icons) {
  font-size: 16px;
}
</style>