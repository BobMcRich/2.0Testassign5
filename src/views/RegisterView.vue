<script setup></script>

<template>
  <div class="hero">
    <div class="overlay">
      <div class="navbar">
        <h1>HeroFLims</h1>
        <a href="index.html" class="button login">Login</a>
      </div>
      <div class="form-container">
        <h2>Create an Account</h2>
        <form>
          <input type="text" placeholder="Name" class="input-field" required>
          <input type="email" placeholder="Email" class="input-field" required>
          <input type="password" placeholder="Password" class="input-field" required>
          <button type="submit" class="button register">Register</button>
        </form>
      </div>
    </div>
  </div>
</template>

<style scoped>

</style>
