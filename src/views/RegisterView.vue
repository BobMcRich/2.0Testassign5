<script setup>
import Footer from '../components/Footer.vue';
</script>

<template>
  <div class="hero">
    <div class="overlay">
      <div class="navbar">
        <h1>SuperFilms</h1>
        <a href="index.html" class="button login">Login</a>
      </div>
      <div class="form-container">
        <h2>Create an Account</h2>
        <form>
          <input type="text" placeholder="Name" class="input-field" required />
          <input type="email" placeholder="Email" class="input-field" required />
          <input type="password" placeholder="Password" class="input-field" required />
          <button type="submit" class="button register">Register</button>
        </form>
      </div>
    </div>
  </div>
  <Footer />
</template>

<style scoped>
/* Hero section with a gradient background */
.hero {
  background: linear-gradient(135deg, #FF6F61, #D83A6A); /* Gradient background */
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh; /* Full viewport height */
  text-align: center;
  position: relative;
  color: white;
  overflow: hidden;
}

/* Overlay to darken the background */
.overlay {
  background: rgba(0, 0, 0, 0.6); /* Dark overlay for contrast */
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  padding: 20px;
  border-radius: 10px;
}

/* Navbar at the top */
.navbar {
  position: absolute;
  top: 20px;
  width: 100%;
  display: flex;
  justify-content: space-between;
  padding: 0 20px;
}

.navbar h1 {
  font-size: 2.5rem;
  font-weight: bold;
}

/* Button styles */
.button {
  background-color: #fff;
  color: #D83A6A;
  padding: 12px 20px;
  font-size: 1rem;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  transition: background-color 0.3s ease, color 0.3s ease;
}

.button:hover {
  background-color: #FF6F61;
  color: white;
}

/* Login button specific styling */
.login {
  font-size: 1.1rem;
}

/* Form container with input fields */
.form-container {
  background-color: rgba(255, 255, 255, 0.85);
  padding: 30px 40px;
  border-radius: 10px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  width: 100%;
  max-width: 400px;
}

/* Form heading */
.form-container h2 {
  font-size: 2rem;
  font-weight: 600;
  margin-bottom: 20px;
  color: #333;
}

/* Input fields */
.input-field {
  width: 100%;
  padding: 12px;
  margin: 10px 0;
  border: 1px solid #ddd;
  border-radius: 5px;
  font-size: 1rem;
  outline: none;
  transition: border 0.3s ease;
}

.input-field:focus {
  border-color: #FF6F61;
}

/* Register button */
.register {
  width: 100%;
  padding: 12px;
  background-color: #FF6F61;
  color: white;
  font-size: 1.2rem;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.register:hover {
  background-color: #D83A6A;
}
</style>
