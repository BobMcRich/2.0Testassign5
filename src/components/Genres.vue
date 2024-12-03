<script setup>
import axios from "axios";
import { ref, onMounted } from 'vue';
import { useRouter } from "vue-router";

const props = defineProps(["genres"]);
const router = useRouter();
const selectedGenre = ref(28);
const response = ref(null);

async function getMovieByGenre() {
  response.value = await axios.get(`https://api.themoviedb.org/3/discover/movie?api_key=${import.meta.env.VITE_TMDB_KEY}&with_genres=${selectedGenre.value}`);
}

function getMovieDetails(id) {
  router.push(`/movies/${id}`)
}

onMounted(async () => {
  response.value = await axios.get(`https://api.themovb.org/3/discover/movie?api_key=${import.meta.env.VITE_TMDB_KEY}&with_genres=${selectedGenre.value}`);
})
</script>

<template>
  <div class="movie-gallery">
    <select v-model="selectedGenre" @change="getMovieByGenre" class="genre-selector">
      <option v-for="genre of genres" :key="genre.id" :value="genre.id">{{ genre.genreName }}</option>
    </select>
    <div v-if="response" class="movie-list">
      <div v-for="movie in response.data.results" :key="movie.id" class="movie-card" @click="getMovieDetails(movie.id)">
        <img :src="`https://image.tmdb.org/t/p/w500${movie.poster_path}`" alt="Movie Poster" class="movie-poster" />
        <p class="movie-title">{{ movie.title }}</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
/* Movie Gallery container */
.movie-gallery {
  background-color: #f4f4f4;
  padding: 20px;
  font-family: 'Arial', sans-serif;
  text-align: center;
}

/* Genre selector dropdown */
.genre-selector {
  padding: 10px 15px;
  margin-bottom: 30px;
  border-radius: 5px;
  border: 1px solid #ddd;
  font-size: 1rem;
  cursor: pointer;
  transition: border-color 0.3s ease;
}

.genre-selector:focus {
  border-color: #FF6F61; /* Highlight border on focus */
}

/* Movie list container */
.movie-list {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  gap: 20px;
  justify-items: center;
}

/* Individual movie card styling */
.movie-card {
  background-color: white;
  border-radius: 10px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  cursor: pointer;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  padding: 10px;
  width: 200px;
  text-align: center;
}

.movie-card:hover {
  transform: scale(1.05);
  box-shadow: 0 6px 15px rgba(0, 0, 0, 0.2);
}

/* Movie poster styling */
.movie-poster {
  width: 100%;
  height: auto;
  border-radius: 8px;
  transition: transform 0.3s ease;
}

.movie-card:hover .movie-poster {
  transform: scale(1.05); /* Slight zoom effect on hover */
}

/* Movie title styling */
.movie-title {
  margin-top: 10px;
  font-size: 1.1rem;
  font-weight: bold;
  color: #333;
  line-height: 1.4;
  text-transform: capitalize;
  text-overflow: ellipsis;
  white-space: nowrap;
  overflow: hidden;
}

/* Responsive Design */
@media (max-width: 768px) {
  .genre-selector {
    width: 100%;
    margin-bottom: 20px;
  }

  .movie-list {
    grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
  }
}
</style>

