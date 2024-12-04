<script setup>
import Genres from "../components/Genres.vue";
import Feature from "../components/Feature.vue";
import Header from "../components/Header.vue";
import Footer from "../components/Footer.vue";
import Hero from "../components/Hero.vue";

const genresList = [
  {
    id: 28,
    genreName: "Action"
  },
  {
    id: 12,
    genreName: "Adventure"
  },
  {
    id: 27,
    genreName: "Horror"
  },
  {
    id: 10751,
    genreName: "Family"
  },
  {
    id: 36,
    genreName: "History"
  },
]
</script>

<template>
  <Header />
  <Hero />
  <div class="movie-container">
    <div class="feature-section">
      <h2>Featured Movies</h2>
      <Feature />
    </div>
    <div class="genre-list">
      <h2>Genres</h2>
      <Genres :genres="genresList" />
    </div>
    <Footer />
  </div>
</template>

<style scoped>
.movie-container {
  display: flex;
  flex-direction: column;
  gap: 30px;
  margin: 0 auto;
  padding: 20px;
  padding-top: 120px; 
  background: linear-gradient(135deg, #2a2a72, #009ffd); 
  background-size: cover; 
  color: white; 
  height: 100vh; 
  overflow-y: auto; 
  position: relative; 
}

.genre-list {
  background-color: rgba(255, 255, 255, 0.9); 
  padding: 20px;
  border-radius: 10px;
  height: auto; 
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1); 
}

.genre-list h2 {
  font-size: 1.5rem;
  color: #333;
  margin-bottom: 20px;
}

.genre-list ul {
  list-style: none;
  padding: 0;
}

.genre-list li {
  background-color: #e2e2e2;
  margin: 5px 0;
  padding: 10px;
  border-radius: 5px;
  color: #333;
  font-size: 1.1rem;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.genre-list li:hover {
  background-color: #ccc;
}

.feature-section {
  background-color: rgba(255, 255, 255, 0.9); 
  padding: 20px;
  border-radius: 10px;
  height: auto; 
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1); 
}

.feature-section h2 {
  font-size: 1.5rem;
  color: #333;
  margin-bottom: 20px;
}

.feature-section .movie-card {
  display: inline-block;
  margin-right: 15px;
  margin-bottom: 20px;
  width: 200px;
  background-color: #f0f0f0;
  border-radius: 10px;
  overflow: hidden;
}

.feature-section .movie-card img {
  width: 100%;
  height: auto;
}

.feature-section .movie-card .movie-title {
  padding: 10px;
  text-align: center;
  background-color: #333;
  color: #fff;
  font-size: 1rem;
  text-transform: uppercase;
}

.movie-container::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: url('https://www.transparenttextures.com/patterns/stardust.png'); /* Star background for extra coolness */
  background-size: cover;
  opacity: 0.1; 
  pointer-events: none;
}
</style>
