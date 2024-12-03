<script setup>
import axios from "axios";
import { useRoute } from "vue-router";

const route = useRoute();
const response = await axios.get(`https://api.themoviedb.org/3/movie/${route.params.id}?api_key=${import.meta.env.VITE_TMDB_KEY}&append_to_response=videos`);
console.log(response.data);
</script>

<template>
  <div class="movie-detail">
    <h1 class="movie-title">{{ response.data.original_title }}</h1>
    <p class="movie-overview">{{ response.data.overview }}</p>
    <p class="movie-release-date">Release Date: {{ response.data.release_date }}</p>
    <a class="movie-site" :href="response.data.homepage" target="_blank">Official Movie Site</a>
    <img :src="`https://image.tmdb.org/t/p/w500${response.data.poster_path}`" alt="Movie Poster" class="movie-poster" />

    <h2 class="trailers-title">Trailers</h2>
    <div class="trailers-container">
      <div v-for="trailer in response.data.videos.results" :key="trailer.id" class="trailer-tile">
        <a :href="`https://www.youtube.com/watch?v=${trailer.key}`" target="_blank">
          <img :src="`https://img.youtube.com/vi/${trailer.key}/hqdefault.jpg`" alt="Trailer" class="trailer-thumbnail" />
        </a>
      </div>
    </div>
  </div>
</template>

<style scoped>
/* Main container for the movie details page */
.movie-detail {
  background-color: #f9f9f9;
  padding: 30px 20px;
  text-align: center;
  font-family: 'Arial', sans-serif;
}

/* Movie title styling */
.movie-title {
  font-size: 2.5rem;
  font-weight: bold;
  color: #333;
  margin-bottom: 20px;
  letter-spacing: 1px;
  text-transform: capitalize;
}

/* Movie overview styling */
.movie-overview {
  font-size: 1.2rem;
  color: #555;
  line-height: 1.6;
  margin-bottom: 30px;
  text-align: justify;
}

/* Movie release date styling */
.movie-release-date {
  font-size: 1.1rem;
  color: #777;
  margin-bottom: 15px;
  font-weight: 600;
}

/* Official movie site link styling */
.movie-site {
  display: inline-block;
  background-color: #FF6F61;
  color: white;
  padding: 12px 20px;
  text-decoration: none;
  border-radius: 5px;
  margin-bottom: 30px;
  transition: background-color 0.3s ease;
}

.movie-site:hover {
  background-color: #D83A6A;
}

/* Movie poster styling */
.movie-poster {
  width: 100%;
  max-width: 300px;
  height: auto;
  border-radius: 10px;
  margin-top: 20px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.movie-poster:hover {
  transform: scale(1.05);
  box-shadow: 0 6px 15px rgba(0, 0, 0, 0.2);
}

/* Trailers title styling */
.trailers-title {
  font-size: 2rem;
  font-weight: 600;
  color: #333;
  margin-top: 50px;
  margin-bottom: 20px;
}

/* Container for the trailer thumbnails */
.trailers-container {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
  gap: 20px;
  justify-items: center;
  margin-top: 30px;
}

/* Individual trailer thumbnail styling */
.trailer-tile {
  position: relative;
  overflow: hidden;
  border-radius: 10px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  cursor: pointer;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.trailer-tile:hover {
  transform: scale(1.05);
  box-shadow: 0 6px 15px rgba(0, 0, 0, 0.2);
}

/* Trailer thumbnail image styling */
.trailer-thumbnail {
  width: 100%;
  height: auto;
  border-radius: 10px;
  transition: transform 0.3s ease;
}

.trailer-tile:hover .trailer-thumbnail {
  transform: scale(1.1);
}

/* Responsive adjustments for smaller screens */
@media (max-width: 768px) {
  .movie-title {
    font-size: 2rem;
  }

  .movie-overview {
    font-size: 1rem;
  }

  .movie-poster {
    max-width: 250px;
  }

  .trailers-title {
    font-size: 1.8rem;
  }
}
</style>
