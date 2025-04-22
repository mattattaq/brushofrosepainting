<script setup>
import { ref } from 'vue';
import { VueperSlides, VueperSlide } from 'vueperslides'
import 'vueperslides/dist/vueperslides.css'

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
        <div class="no-wrap center-content">
            <div class="gallery-grid">
                <vueper-slides :gap="3" class="no-shadow" :visible-slides="4" :slide-ratio="1 / 4" :bullets="false"
                    :dragging-distance="70" fixed-height="320px" :infinite="true">
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
