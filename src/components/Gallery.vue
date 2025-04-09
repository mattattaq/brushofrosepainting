<script setup>
import { ref } from 'vue';

const images = ref([
    {
        src: 'https://picsum.photos/200/300',
        alt: 'Image 1'
    },
    {
        src: 'https://picsum.photos/200/300',
        alt: 'Image 2'
    },
    {
        src: 'https://picsum.photos/200/300',
        alt: 'Image 3'
    },
    {
        src: 'https://picsum.photos/200/300',
        alt: 'Image 4'
    },
    {
        src: 'https://picsum.photos/200/300',
        alt: 'Image 5'
    },
    {
        src: 'https://picsum.photos/200/300',
        alt: 'Image 6'
    },
    {
        src: 'https://picsum.photos/200/300',
        alt: 'Image 7'
    },
    {
        src: 'https://picsum.photos/200/300',
        alt: 'Image 8'
    },
    {
        src: 'https://picsum.photos/200/300',
        alt: 'Image 9'
    },
    {
        src: 'https://picsum.photos/200/300',
        alt: 'Image 10'
    },
    {
        src: 'https://picsum.photos/200/300',
        alt: 'Image 11'
    }])
</script>

<template>
    <section id="gallery">
        <div class="container">
            <h2>Gallery</h2>
            <div class="gallery-grid">
                <div class="gallery-item" v-for="image in images" :key="image.src">
                    <img v-lazy="image.src" :alt="image.alt" />
                </div>
            </div>
        </div>
    </section>
</template>

<style scoped>
.gallery-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 5px;
    justify-content: center;
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
    padding-bottom: 24px;
}
</style>
