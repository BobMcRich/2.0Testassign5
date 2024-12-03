<script setup>
import { RouterLink } from 'vue-router';
import Header from '../components/Header.vue';
import Feature from '../components/Feature.vue';
import Hero from '../components/Hero.vue';
import Footer from '../components/Footer.vue';
</script>

<template>
    <div>
        <button class="language-btn">English</button>
        <RouterLink to="/register" class="button register">Register</RouterLink>
        <RouterLink to="/login" class="button login">Login</RouterLink>
       <Header />
       <Feature />
       <Hero />
       <Footer />
    </div>
</template>

<style scoped>
/* General button styles */
.button, .language-btn {
  background-color: #FF6F61; /* Red background for buttons */
  color: white; /* Text color */
  padding: 12px 20px;
  font-size: 1.1rem;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  display: inline-block;
  transition: all 0.3s ease;
  margin: 10px;
}

/* Hover effect for buttons */
.button:hover, .language-btn:hover {
  background-color: #D83A6A; /* Slightly darker shade on hover */
  transform: scale(1.05); /* Scale up slightly on hover */
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2); /* Add a shadow effect */
}

/* Styles for Register button specifically */
.register {
  background-color: #4CAF50; /* Green color for register button */
}

.register:hover {
  background-color: #45a049; /* Darker green on hover */
}

/* Styles for Login button specifically */
.login {
  background-color: #2196F3; /* Blue color for login button */
}

.login:hover {
  background-color: #0b7dda; /* Darker blue on hover */
}

/* Language button styling */
.language-btn {
  background-color: #FFB74D; /* Light orange for language button */
  font-weight: bold;
  margin-top: 20px;
}

.language-btn:hover {
  background-color: #FB8C00; /* Darker orange on hover */
}
</style>
