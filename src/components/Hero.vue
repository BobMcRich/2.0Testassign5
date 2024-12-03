<script setup>
</script>

<template>
  <div class="movies-section">
    <h2 class="title">Top Rated Movies</h2>
    <div class="movies">
      <!-- Movie Cards will be added here -->
      <div class="movie-card">
        <img src="https://via.placeholder.com/200x300" alt="Movie Title" class="movie-image" />
        <div class="movie-info">
          <h3>Movie Title</h3>
          <p>⭐ 9.8/10</p>
        </div>
      </div>
      <!-- Repeat similar cards for more movies -->
    </div>
  </div>
</template>

<style scoped>
/* Container for the entire movie section */
.movies-section {
  padding: 40px 20px;
  background-color: #f5f5f5;
  text-align: center;
}

/* Title for the top-rated movies section */
.title {
  font-size: 2.5rem;
  font-weight: 600;
  color: #333;
  margin-bottom: 30px;
  letter-spacing: 1px;
  text-transform: uppercase;
  font-family: 'Roboto', sans-serif;
}

/* Flexbox container for the movie cards */
.movies {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
  gap: 20px;
  justify-items: center;
}

/* Style for each individual movie card */
.movie-card {
  background-color: #fff;
  border-radius: 10px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  width: 100%;
  max-width: 220px;
  cursor: pointer;
}

.movie-card:hover {
  transform: scale(1.05);
  box-shadow: 0 6px 15px rgba(0, 0, 0, 0.2);
}

/* Style for the movie poster image */
.movie-image {
  width: 100%;
  height: 300px;
  object-fit: cover;
  border-bottom: 2px solid #eee;
}

/* Movie information (title and rating) */
.movie-info {
  padding: 15px;
  text-align: left;
}

.movie-info h3 {
  font-size: 1.2rem;
  color: #333;
  font-weight: 500;
  margin-bottom: 5px;
  text-transform: capitalize;
}

.movie-info p {
  font-size: 1rem;
  color: #FF6F61;
  font-weight: 600;
}

/* Responsive adjustments for smaller screens */
@media (max-width: 768px) {
  .movies {
    grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
  }

  .movie-card {
    max-width: 180px;
  }

  .title {
    font-size: 2rem;
  }
}
</style>
