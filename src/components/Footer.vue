<script setup>
</script>

<template>
  <div class="footer">
    <p class="footer-text">HeroFilms, 2024</p>
    <p class="author">Author: <a href="mailto:Samuel.li2@student.tdsb.on.ca">Samuel.li2@student.tdsb.on.ca</a></p>
  </div>
</template>

<style scoped>
/* Footer container styles */
.footer {
  background-color: #222;
  color: #fff;
  padding: 30px 20px;
  text-align: center;
  font-family: 'Arial', sans-serif;
  position: fixed;
  bottom: 0;
  width: 100%;
  z-index: 10;
}

/* Footer text styles */
.footer-text {
  font-size: 1.2rem;
  font-weight: 400;
  letter-spacing: 1px;
  margin: 0;
  opacity: 0.8;
  transition: opacity 0.3s ease;
}

/* Hover effect on footer text */
.footer-text:hover {
  opacity: 1;
}

/* Author section styling */
.author {
  font-size: 1rem;
  margin-top: 10px;
  opacity: 0.7;
}

/* Link styling */
.author a {
  color: #FF6F61;
  text-decoration: none;
  transition: color 0.3s ease;
}

.author a:hover {
  color: #D83A6A;
}
</style>
