<template>
  <div class="menu-container">
    <div class="menu">
      <router-link to="/" class="menu-item">
        <span class="material-icons">home</span>
        <span>Home</span>
      </router-link>
      <router-link to="/orders" class="menu-item">
        <span class="material-icons">shopping_cart</span>
        <span>Orders</span>
      </router-link>
      <router-link to="/profile" class="menu-item">
        <span class="material-icons">person</span>
        <span>Profile</span>
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
  bottom: 0;
  left: 0;
  width: 100%;
  background: #ffffff;
  box-shadow: 0 -2px 10px rgba(0, 0, 0, 0.1);
}

.menu {
  display: flex;
  justify-content: space-around;
  padding: 10px 0;
}

.menu-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-decoration: none;
  color: #666;
}

.menu-item.router-link-active {
  color: #42b983;
}

.material-icons {
  font-size: 24px;
}
</style>