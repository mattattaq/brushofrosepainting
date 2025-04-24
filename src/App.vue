<script setup>
import { onMounted } from 'vue';
import Header from './components/Header.vue';
import Splash from './components/Splash.vue';
import Gallery from './components/Gallery.vue';
import Book from './components/Book.vue';
import About from './components/About.vue';
import Footer from './components/Footer.vue';

onMounted(() => {
  const elements = document.querySelectorAll('.fade-in');

  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.classList.add('visible');
        }
      });
    },
    { threshold: 0.3 } // Element becomes visible when 30% of it is in view
  );

  elements.forEach((el) => observer.observe(el));
});
</script>

<template>
  <Header />
  <Splash />
  <About />
  <Gallery />
  <Book />
  <Footer />
</template>

<style scoped></style>
