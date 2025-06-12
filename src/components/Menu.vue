<template>
  <div class="menu-overlay" v-if="isMenuOpen" @click="toggleMenu"></div>
  <div class="menu-button" @click="toggleMenu">
    <span class="material-icons">{{ isMenuOpen ? 'close' : 'menu' }}</span>
  </div>
  <div class="menu-container" :class="{ 'menu-open': isMenuOpen }">
    <div class="logo">
      <img src="../assets/logo.png" alt="WeDeliver99 Logo" />
    </div>
    <div class="menu">
      <router-link to="/dashboard" class="menu-item" @click="closeMenuOnMobile">
        <span class="material-icons">dashboard</span>
        <span>Dashboard</span>
      </router-link>
      <router-link to="/clients" class="menu-item" @click="closeMenuOnMobile">
        <span class="material-icons">groups</span>
        <span>Clients</span>
      </router-link>
      <router-link to="/orders" class="menu-item" @click="closeMenuOnMobile">
        <span class="material-icons">shopping_cart</span>
        <span>Orders</span>
      </router-link>
      <router-link to="/drivers" class="menu-item" @click="closeMenuOnMobile">
        <span class="material-icons">local_shipping</span>
        <span>Drivers</span>
      </router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Menu',
  data() {
    return {
      isMenuOpen: false
    }
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen
    },
    closeMenuOnMobile() {
      if (window.innerWidth <= 768) {
        this.isMenuOpen = false
      }
    }
  }
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
  z-index: 1000;
}

.menu-button {
  display: none;
  position: fixed;
  top: 10px;
  left: 10px;
  z-index: 1001;
  background: var(--primary-color);
  border-radius: 50%;
  width: 40px;
  height: 40px;
  justify-content: center;
  align-items: center;
  cursor: pointer;
  color: white;
}

.menu-overlay {
  display: none;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.5);
  z-index: 999;
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

@media (max-width: 768px) {
  .menu-button {
    display: flex;
  }

  .menu-container {
    transform: translateX(-100%);
    transition: transform 0.3s ease;
  }

  .menu-container.menu-open {
    transform: translateX(0);
  }

  .menu-overlay {
    display: block;
    opacity: 0;
    pointer-events: none;
    transition: opacity 0.3s ease;
  }

  .menu-overlay {
    opacity: 1;
    pointer-events: auto;
  }
}
</style>