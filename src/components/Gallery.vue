<script setup>
import { ref, onMounted, onUnmounted } from 'vue';
import { VueperSlides, VueperSlide } from 'vueperslides'
import 'vueperslides/dist/vueperslides.css'
import bear from '../assets/bear.jpg'
import foreverHome from '../assets/forever-home.jpg'
import hair from '../assets/hair.jpg'
import misty from '../assets/misty.jpg'
import muralYoga from '../assets/mural-yoga.jpg'
import mural from '../assets/mural.jpg'
import spa2 from '../assets/spa-2.jpg'
import spa from '../assets/spa.jpg'
import bear2 from '../assets/bear-2.jpg'

const images = ref([
    { src: bear, alt: 'Image 1' },
    { src: foreverHome, alt: 'Image 2' },
    { src: hair, alt: 'Image 3' },
    { src: misty, alt: 'Image 4' },
    { src: muralYoga, alt: 'Image 5' },
    { src: mural, alt: 'Image 6' },
    { src: spa2, alt: 'Image 7' },
    { src: spa, alt: 'Image 8' },
    { src: bear2, alt: 'Image 9' }
])

const visibleSlides = ref(4)

const updateVisibleSlides = () => {
    const width = window.innerWidth || document.documentElement.clientWidth

    if (width < 600) {
        visibleSlides.value = 2
    } else if (width < 768) {
        visibleSlides.value = 3
    } else {
        visibleSlides.value = 4
    }
}

// Basic debounce utility
function debounce(fn, delay = 150) {
    let timeout
    return (...args) => {
        clearTimeout(timeout)
        timeout = setTimeout(() => {
            fn(...args)
        }, delay)
    }
}

const debouncedUpdate = debounce(updateVisibleSlides)

onMounted(() => {
    updateVisibleSlides()
    window.addEventListener('resize', debouncedUpdate)
})

onUnmounted(() => {
    window.removeEventListener('resize', debouncedUpdate)
})
</script>

<template>
    <section id="gallery" class="fade-in">
        <div class="no-wrap center-content">
            <div class="gallery-grid">
                <vueper-slides :gap="3" class="no-shadow" :touchable="false" :visible-slides="visibleSlides"
                    :slide-ratio="1 / visibleSlides" :bullets="false" fixed-height="320px" :infinite="true">
                    <vueper-slide v-for="image in images" :key="image.alt" :image="image.src" />
                </vueper-slides>
            </div>
        </div>
    </section>
</template>

<style scoped>
.gallery-grid {
    width: calc(100% - 100px);
    margin-left: 50px;
}

.no-wrap {
    flex-direction: column;
    align-items: center;
    width: 100%;
}

.gallery-item {
    width: 100%;
    height: 100%;
    max-width: 300px;
    max-height: 300px;
    flex: 1 1 300px;
}

.gallery-item img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

#gallery {
    background-color: var(--neutral);
    min-height: auto;
    padding-top: 12px;
    padding-bottom: 12px;
}

#gallery .vueperslides--fixed-height.vueperslides--bullets-outside {
    margin-bottom: unset !important;
}

.vueperslide--visible:hover {
    filter: grayscale(100%);
}
</style>
