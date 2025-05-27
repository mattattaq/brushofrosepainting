<script setup>
import { ref, onMounted, onUnmounted, watch, computed } from 'vue'

import bear from '../assets/bear.jpg'
import foreverHome from '../assets/forever-home.jpg'
import hair from '../assets/hair.jpg'
import misty from '../assets/misty.jpg'
import muralYoga from '../assets/mural-yoga.jpg'
import mural from '../assets/mural.jpg'
import spa2 from '../assets/spa-2.jpg'
import spa from '../assets/spa.jpg'
import bear2 from '../assets/bear-2.jpg'
import cabBefore from '../assets/cabinets-before.jpg'
import cabAfter from '../assets/cabinet-after.jpg'

const images = ref([
    { src: bear, alt: 'A bear relaxing' },
    { src: foreverHome, alt: 'Welcome to our forever home!' },
    { src: hair, alt: 'Salon Mural' },
    { src: misty, alt: 'Photorealistic woodblock painting of Misty' },
    { src: muralYoga, alt: 'Yoga mural' },
    { src: mural, alt: 'Colorful animal mural on the side of a trailer' },
    { src: spa2, alt: 'Skin Remedy sunset mural' },
    { src: spa, alt: 'Silver Door Spa logo painting' },
    { src: bear2, alt: 'Another bear picture' },
    { src: cabBefore, alt: 'Cabinet painting before' },
    { src: cabAfter, alt: 'Cabinet painting after' }
])

const columns = ref(4)

const currentIndex = ref(null)
const selectedImage = computed(() =>
    currentIndex.value !== null ? images.value[currentIndex.value] : null
)

const openModal = (index) => {
    currentIndex.value = index
}

const closeModal = () => {
    currentIndex.value = null
}

const showNext = () => {
    if (currentIndex.value !== null) {
        currentIndex.value = (currentIndex.value + 1) % images.value.length
    }
}

const showPrev = () => {
    if (currentIndex.value !== null) {
        currentIndex.value =
            (currentIndex.value - 1 + images.value.length) % images.value.length
    }
}

// Prevent body scroll when modal is open
watch(currentIndex, (newVal) => {
    if (newVal !== null) {
        document.body.style.overflow = 'hidden'
    } else {
        document.body.style.overflow = ''
    }
})

const updateColumns = () => {
    const width = window.innerWidth || document.documentElement.clientWidth
    if (width < 600) {
        columns.value = 2
    } else if (width < 768) {
        columns.value = 3
    } else {
        columns.value = 4
    }
}

const debounce = (fn, delay = 150) => {
    let timeout
    return (...args) => {
        clearTimeout(timeout)
        timeout = setTimeout(() => fn(...args), delay)
    }
}

const debouncedUpdate = debounce(updateColumns)

onMounted(() => {
    updateColumns()
    window.addEventListener('resize', debouncedUpdate)
})

onUnmounted(() => {
    window.removeEventListener('resize', debouncedUpdate)
    document.body.style.overflow = ''
})
</script>

<template>
    <section id="gallery" class="fade-in">
        <div id="gallery-grid" class="gallery-grid" :style="{ gridTemplateColumns: `repeat(${columns}, 1fr)` }">
            <div v-for="(image, index) in images" :key="image.alt" class="gallery-item" @click="openModal(index)">
                <img :src="image.src" :alt="image.alt" />
            </div>
        </div>

        <!-- Modal -->
        <div v-if="selectedImage" class="modal-overlay" @click.self="closeModal">
            <div class="modal-content">
                <button class="modal-close" @click="closeModal">×</button>
                <img :src="selectedImage.src" :alt="selectedImage.alt" class="modal-image" />
                <p class="caption">{{ selectedImage.alt }}</p>
                <button class="nav-button left" @click.stop="showPrev">‹</button>
                <button class="nav-button right" @click.stop="showNext">›</button>
            </div>
        </div>
    </section>
</template>

<style scoped>
#gallery {
    display: contents;
}

.gallery-grid {
    display: grid;
    gap: 12px;
    width: calc(100% - 100px);
    margin-left: 50px;
    margin-bottom: 24px;
}

.gallery-item {
    cursor: pointer;
    overflow: hidden;
}

.gallery-item img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: filter 0.2s;
}

.gallery-item img:hover {
    filter: grayscale(100%);
}

.modal-overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    background-color: rgba(0, 0, 0, 0.85);
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 1000;
}

.modal-content {
    position: relative;
    max-width: 90%;
    max-height: 90%;
    text-align: center;
    background: white;
    padding: 1rem;
    border-radius: 8px;
    overflow: hidden;
    display: flex;
    flex-direction: column;
    align-items: center;
}

.modal-image {
    max-width: 100%;
    max-height: 70vh;
    margin-bottom: 0.75rem;
}

.caption {
    font-size: 1rem;
    color: #333;
}

.modal-close {
    position: absolute;
    top: 0.5rem;
    right: 0.75rem;
    font-size: 2rem;
    background: transparent;
    border: none;
    color: #000;
    cursor: pointer;
}

.nav-button {
    position: absolute;
    top: 50%;
    font-size: 2rem;
    background: rgba(255, 255, 255, 0.7);
    border: none;
    padding: 0.5rem 1rem;
    cursor: pointer;
    transform: translateY(-50%);
    user-select: none;
    z-index: 1;
}

.nav-button.left {
    left: -2rem;
}

.nav-button.right {
    right: -2rem;
}
</style>
