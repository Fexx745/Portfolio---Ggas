<script setup lang="ts">
import { useI18n } from "vue-i18n";
const { t } = useI18n();
import 'vue3-carousel/carousel.css';
import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel';

import image1 from '@/assets/images/caroucel/1.png'
import image2 from '@/assets/images/caroucel/2.png'
import image3 from '@/assets/images/caroucel/3.png'

const carouselImages = [
    { src: image1, alt: "Image 1", description: "Internal Project Management System Development" },
    { src: image2, alt: "Image 2", description: "E-commerce Website Development Project #1" },
    { src: image3, alt: "Image 3", description: "E-commerce Website Development Project #2" }
];
const carouselConfig = {
    itemsToShow: 2.5,
    wrapAround: true
};
const showDialog = ref(false);
const selectedImage = ref(null);

const openDialog = (image: any) => {
    selectedImage.value = image;
    showDialog.value = true;
};

const closeDialog = () => {
    showDialog.value = false;
};
</script>

<template>
    <v-container>
        <v-chip size="x-large" class="mb-10" color="primary">
            <h3>{{ t('project.exampleImg') }}</h3>
        </v-chip>
        <Carousel v-bind="carouselConfig" :autoplay="800" :interval="3000" :transition="500">
            <Slide v-for="(item, index) in carouselImages" :key="index">
                <div class="carousel__item" @click="openDialog(item.src)">
                    <img :src="item.src" :alt="item.alt" class="carousel-image" />
                    <div class="box-item">
                        <p>{{ item.description }}</p>
                    </div>
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

    <v-dialog v-model="showDialog" max-width="600">
        <v-card>
            <v-card-title class="d-flex justify-end">
                <v-btn icon="mdi-close" @click="closeDialog"></v-btn>
            </v-card-title>
            <v-card-text class="d-flex justify-center">
                <v-img v-if="selectedImage" :src="selectedImage" class="modal-image" contain></v-img>
            </v-card-text>
        </v-card>
    </v-dialog>
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
    border-radius: 8px;
    width: 400px;
    cursor: pointer;
}

.box-item h3 {
    margin: 0;
    font-size: 1.2rem;
}

.detail-box {
    max-height: 200px;
    overflow: hidden;
    text-overflow: ellipsis;
    padding: 10px;
    border: 1px solid #ddd;
    border-radius: 8px;
}

.detail-box p {
    margin: 0;
}
</style>
