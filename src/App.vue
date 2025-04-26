<script setup>
import { onMounted } from 'vue';
import Header from './components/Header.vue';
import Splash from './components/Splash.vue';
import Gallery from './components/Gallery.vue';
import Book from './components/Book.vue';
import About from './components/About.vue';
import FAQs from './components/FAQs.vue';
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
    { threshold: 0.3 }
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
  <FAQs />
  <Footer />
</template>

<style scoped></style>
