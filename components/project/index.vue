<script setup lang="ts">
import { useI18n } from "vue-i18n";
const { t } = useI18n();
import 'vue3-carousel/carousel.css';
import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel';

import profileImage from '@/assets/images/caroucel/1.png';

const carouselImages = [
    { src: "@assets/images/carousel/1.png", alt: "Image 1" },
    { src: "@assets/images/carousel/1.png", alt: "Image 2" },
    { src: "@assets/images/carousel/1.png", alt: "Image 3" },
    { src: "@assets/images/carousel/1.png", alt: "Image 4" },
    { src: "@assets/images/carousel/1.png", alt: "Image 5" },
];

const carouselConfig = {
    itemsToShow: 2.5,
    wrapAround: true
};
</script>

<template>
    <v-container>
        <Carousel v-bind="carouselConfig">
            <Slide v-for="(image, index) in carouselImages" :key="index">
                <div class="carousel__item">
                    <img :src="profileImage" alt="Carousel Image" class="carousel-image" />
                </div>
            </Slide>

            <template #addons>
                <Navigation />
                <Pagination />
            </template>
        </Carousel>
        <v-row>
            <v-col>
                <h1>{{ t('welcomeMessage') }}</h1>
                <p>{{ t('description') }}</p>
            </v-col>
        </v-row>
    </v-container>
</template>

<style scoped>
h1 {
    color: #3f51b5;
    text-align: center;
    margin-top: 20px;
}

p {
    color: #757575;
    text-align: center;
    margin-top: 10px;
}

.carousel__item {
    display: flex;
    justify-content: center;
    align-items: center;
}

.carousel-image {
    width: 100%;
    height: auto;
    border-radius: 10px;
}
</style>
