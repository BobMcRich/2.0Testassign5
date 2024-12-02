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

</style>