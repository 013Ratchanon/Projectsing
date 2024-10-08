<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <!-- Logo Image -->
    <img alt="Sing Manga Logo" class="logo" src="@/assets/sing.png" width="125" height="40" />

    <nav>
      <!-- Navigation Links -->
      <RouterLink to="/">หน้าหลัก</RouterLink>
      <RouterLink to="/help">ช่วยเหลือ</RouterLink>
      <RouterLink to="/all-manga">มังงะทั้งหมด</RouterLink>
      <RouterLink to="/followed-manga">มังงะที่ติดตาม</RouterLink>
      <RouterLink to="/submit-translation">ฝากผลงานแปล</RouterLink>
    </nav>
  </header>

  <!-- Main Content -->
  <RouterView />
</template>

<style scoped>
header {
  background-color: #121212; /* Dark background as in the image */
  padding: 1rem 2rem;
  display: flex;
  align-items: center;
  justify-content: space-between;
  position: fixed; /* Makes the header stick to the top */
  top: 0;
  left: 0;
  width: 100%;
  z-index: 1000; /* Ensures the header stays above other content */
}

.logo {
  display: block;
}

nav {
  display: flex;
  gap: 2rem;
  font-size: 16px;
}

nav a {
  color: white;
  text-decoration: none;
}

nav a:hover {
  color: #f00; /* Hover effect in red */
}

@media (max-width: 768px) {
  nav {
    flex-direction: column;
    align-items: center;
  }
}

body {
  padding-top: 80px; /* Add padding to prevent content from being hidden under the fixed header */
}
</style>
<style scoped>
header {
  background-color: #121212;
  /* Dark background as in the image */
  padding: 1rem 2rem;
  display: flex;
  align-items: center;
  justify-content: space-between;
  position: fixed;
  /* Makes the header stick to the top */
  top: 0;
  left: 0;
  width: 100%;
  z-index: 1000;
  /* Ensures the header stays above other content */
}

.logo {
  display: block;
}

nav {
  display: flex;
  gap: 2rem;
  font-size: 16px;
}

nav a {
  color: white;
  text-decoration: none;
  position: relative;
  /* Needed for ::after positioning */
}

nav a:hover {
  color: #f00;
  /* Hover effect in red */
}


nav a[href="/help"]:hover::after {
  content: 'แจ้งปัญหา';
  position: absolute;
  top: 100%;
  /* Position below the link */
  left: 50%;
  transform: translateX(-50%);
  background-color: #333;
  color: white;
  padding: 0.5rem;
  border-radius: 5px;
  white-space: nowrap;
}

@media (max-width: 768px) {
  nav {
    flex-direction: column;
    align-items: center;
  }
}

body {
  padding-top: 80px;
  /* Add padding to prevent content from being hidden under the fixed header */
}
</style>
