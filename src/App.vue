<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <!-- Header -->
  <header>
    <img alt="Sing Manga Logo" class="logo" src="@/assets/sing.png" width="125" height="40" />
    <nav>
      <RouterLink to="/">หน้าหลัก</RouterLink>
      <RouterLink to="/help">ช่วยเหลือ</RouterLink>
      <RouterLink to="/all-manga">มังงะทั้งหมด</RouterLink>
      <RouterLink to="/followed-manga">มังงะที่ติดตาม</RouterLink>
      <RouterLink to="/submit-translation">ฝากผลงานแปล</RouterLink>
    </nav>
  </header>

  <!-- Main Content -->
  <RouterView />

  <!-- Manga Cards Section -->
  <div class="manga-container">
    <div class="manga-card" v-for="manga in mangas" :key="manga.id">
      <img :src="manga.image" alt="Manga Cover" class="manga-image" />
      <div class="manga-details">
        <h3>{{ manga.title }}</h3>
        <p>Chapter: {{ manga.latestChapter }}</p>
        <div class="chapter-buttons">
          <button v-for="chapter in manga.chapters" :key="chapter" class="chapter-btn">
            Chapter {{ chapter }}
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      mangas: [
        {
          id: 1,
          title: "Childhood Friend Zenith",
          latestChapter: 21,
          chapters: [21, 20, 19],
          image: "https://example.com/childhood-friend-zenith.jpg",
        },
        {
          id: 2,
          title: "Ghost Story Club (Remake)",
          latestChapter: 8,
          chapters: [8, 7, 6],
          image: "https://example.com/ghost-story-club.jpg",
        },
        {
          id: 3,
          title: "My Second Life a Healing Life?",
          latestChapter: 6,
          chapters: [6, 5, 4],
          image: "https://example.com/second-life-healing.jpg",
        },
        {
          id: 4,
          title: "Healing Life Through Camping in Another World",
          latestChapter: 31,
          chapters: [31, 30, 29],
          image: "https://example.com/healing-life.jpg",
        },
        {
          id: 5,
          title: "The Last Adventurer",
          latestChapter: 40,
          chapters: [40, 39, 38],
          image: "https://example.com/last-adventurer.jpg",
        },
      ],
    };
  },
};
</script>

<style scoped>
/* Header Styles */
header {
  background-color: #121212;
  padding: 1rem 2rem;
  display: flex;
  align-items: center;
  justify-content: space-between;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 1000;
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
  color: #f00;
}

/* Manga Cards Styles */
.manga-container {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  justify-content: space-evenly;
  padding-top: 80px;
}

.manga-card {
  background-color: #1f1f1f;
  color: white;
  border-radius: 10px;
  padding: 20px;
  width: 200px;
  text-align: center;
}

.manga-image {
  width: 100%;
  height: auto;
  border-radius: 10px;
}

.manga-details {
  margin-top: 10px;
}

.chapter-buttons {
  display: flex;
  flex-direction: column;
  gap: 10px;
  margin-top: 10px;
}

.chapter-btn {
  background-color: #333;
  color: white;
  border: none;
  padding: 10px;
  cursor: pointer;
  border-radius: 5px;
}

.chapter-btn:hover {
  background-color: #f00;
}
</style>
