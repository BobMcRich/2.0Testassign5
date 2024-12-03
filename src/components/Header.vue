<script setup>
</script>

<template>
  <div class="hero">
    <div class="hero-content">
      <h1>SuperFlims</h1>
      <p>Where Every Film Finds Its Hero.</p>
    </div>
  </div>
</template>

<style scoped>
.hero {
  background: linear-gradient(135deg, #FF6F61, #D83A6A);
  display: flex;
  justify-content: center;
  align-items: center;
  height: 50vh; 
  text-align: center;
  position: relative;
  color: white;
  overflow: hidden;
  padding: 20px; 
}


.hero-content {
  z-index: 2;
  padding: 20px; /* Reduced padding inside the content box */
  backdrop-filter: blur(5px); /* Slight blur effect */
  border-radius: 12px;
  width: 90%; /* Limiting the width for a more compact look */
  max-width: 500px; /* Setting a maximum width for the content */
}

/* Hero text (title) */
.hero h1 {
  font-size: 2.5rem; /* Smaller font size */
  font-family: 'Roboto', sans-serif;
  font-weight: bold;
  text-transform: uppercase;
  letter-spacing: 1px; /* Reduced spacing */
  animation: fadeIn 2s ease-out;
}

/* Subtitle text */
.hero p {
  font-size: 1.25rem; /* Smaller subtitle size */
  font-family: 'Arial', sans-serif;
  margin-top: 10px;
  font-weight: 300;
  letter-spacing: 0.5px;
  opacity: 0.8;
}

/* Add a subtle fade-in animation */
@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

/* Adding some animated background stars or particles */
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
