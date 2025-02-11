<script setup lang="ts">
import { useI18n } from "vue-i18n";
import { onMounted } from 'vue';
const { t } = useI18n();
import 'vue3-carousel/carousel.css';
import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel';

import image1 from '@/assets/images/caroucel/1.png'
import image2 from '@/assets/images/caroucel/2.png'
import image3 from '@/assets/images/caroucel/3.png'

const carouselImages = [
    { src: image1, alt: "Image 1", description: "Description for Image 1" },
    { src: image2, alt: "Image 2", description: "Description for Image 2" },
    { src: image3, alt: "Image 3", description: "Description for Image 3" }
];
const carouselConfig = {
    itemsToShow: 2.5,
    wrapAround: true
};
</script>

<template>
    <v-container>
        <v-chip size="x-large" class="mb-10" color="primary">
            <h3>{{ t('project.exampleImg') }}</h3>
        </v-chip>
        <Carousel v-bind="carouselConfig" :autoplay="800" :interval="3000" :transition="500">
            <Slide v-for="(item, index) in carouselImages" :key="index">
                <div class="carousel__item">
                    <img :src="item.src" :alt="item.alt" class="carousel-image" />
                        <!-- <div class="box-item">
                            <h3>Box Item {{ index + 1 }}</h3>
                            <p>{{ item.description }}</p>
                        </div> -->
                </div>
            </Slide>
            <template #addons>
                <Navigation />
                <Pagination />
            </template>
        </Carousel>
        <v-row>
            <!-- <v-col cols="12" md="12">
                <h5>{{ t('project.des.title') }}</h5>
            </v-col> -->
            <v-col cols="12" md="12" class="mt-10">
                <v-row>
                    <v-col cols="12" md="6">
                        <strong class="kanit-regular">
                            {{ t('project.des.e-com.role') }}&nbsp;
                        </strong>
                        <strong class="kanit-medium">Rajamangala University Of Technology Isan</strong>
                        <div class="detail-box mt-3">
                            <strong class="kanit-medium">{{ t('project.des.e-com.title') }}</strong>
                            <p>{{ t('project.des.e-com.detail') }}</p>
                        </div>
                    </v-col>
                    <v-col cols="12" md="6">
                        <strong class="kanit-regular">
                            {{ t('project.des.mytask.role') }}&nbsp;
                        </strong>
                        <strong class="kanit-medium">Revel Soft</strong>
                        <div class="detail-box mt-3">
                            <strong class="kanit-medium">{{ t('project.des.mytask.title') }}</strong>
                            <p>{{ t('project.des.mytask.detail') }}</p>
                        </div>
                    </v-col>
                </v-row>
            </v-col>
        </v-row>
    </v-container>
</template>

<style scoped>
.carousel__item {
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    cursor: pointer;
}

.carousel-image {
    width: 100%;
    height: auto;
    object-fit: cover;
    border-radius: 8px;
}

.box-item {
    position: absolute;
    bottom: 30px;
    left: 50%;
    transform: translateX(-50%);
    background-color: rgba(0, 0, 0, 0.5);
    color: white;
    padding: 20px;
    border-radius: 8px;
    width: 250px;
    cursor: pointer;
}

.box-item h3 {
    margin: 0;
    font-size: 1.2rem;
}

.box-item p {
    margin: 10px 0 0;
    font-size: 1rem;
    color: #fff;
}

.detail-box {
    max-height: 200px;
    overflow: hidden;
    text-overflow: ellipsis;
    padding: 10px;
    border: 1px solid #ddd;
    border-radius: 8px;
    background-color: #f9f9f9;
}

.detail-box p {
    margin: 0;
}
</style>
