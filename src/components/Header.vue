<script setup>
import { ref } from 'vue';
import { RouterLink } from 'vue-router';

const isLoggedIn = ref(false); // Add the login state for conditional rendering
</script>

<template>
  <div class="hero">
    <div class="hero-content">
      <h1>SuperFlims</h1>
      <div class="button-group">
        <button class="language-btn">English</button>
        <RouterLink v-if="!isLoggedIn" to="/register" class="button register">Register</RouterLink>
        <RouterLink v-if="!isLoggedIn" to="/login" class="button login">Login</RouterLink>
      </div>
    </div>
  </div>
</template>

<style scoped>
.hero {
  background: linear-gradient(135deg, #FF6F61, #D83A6A);
  display: flex;
  justify-content: center;
  align-items: center;
  height: 40vh; /* Reduced height */
  position: relative;
  color: white;
  overflow: hidden;
  padding: 20px; 
}

.hero-content {
  z-index: 2;
  display: flex;
  justify-content: space-between; /* Spread the title and buttons apart */
  align-items: center;
  width: 100%;
  max-width: 1200px; /* Optional: You can adjust this max-width to control the content width */
}

.hero h1 {
  font-size: 2.5rem; /* Slightly smaller font size */
  font-family: 'Roboto', sans-serif;
  font-weight: bold;
  text-transform: uppercase;
  letter-spacing: 1px; 
}

.button-group {
  display: flex;
  align-items: center;
}

.language-btn, .button {
  background-color: #FF6F61;
  color: white;
  padding: 12px 20px;
  font-size: 1.1rem;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  display: inline-block;
  transition: all 0.3s ease;
  margin-left: 10px; /* Add spacing between the buttons */
}

.button:hover, .language-btn:hover {
  background-color: #D83A6A;
  transform: scale(1.05);
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
}

.register {
  background-color: #4CAF50;
}

.register:hover {
  background-color: #45a049;
}

.login {
  background-color: #2196F3;
}

.login:hover {
  background-color: #0b7dda;
}

.language-btn {
  background-color: #FFB74D;
  font-weight: bold;
}

.language-btn:hover {
  background-color: #FB8C00;
}

.hero::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: url('https://www.transparenttextures.com/patterns/star-animated.gif'); /* Animated stars */
  background-size: cover;
  opacity: 0.2;
  pointer-events: none;
}
</style>
