<script setup lang="ts">
import { useI18n } from "vue-i18n";
const { t } = useI18n();
import 'vue3-carousel/carousel.css';
import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel';

import image1 from '@/assets/images/caroucel/1.jpg'
import image2 from '@/assets/images/caroucel/2.jpg'
import image3 from '@/assets/images/caroucel/3.jpg'
import image4 from '@/assets/images/caroucel/4.jpg'
import image5 from '@/assets/images/caroucel/5.jpg'
import image6 from '@/assets/images/caroucel/6.jpg'
import image7 from '@/assets/images/caroucel/7.jpg'
import image8 from '@/assets/images/caroucel/8.png'
import image9 from '@/assets/images/caroucel/9.png'

const carouselImagesEcom = [
    { src: image8, alt: "Image 8", description: "" },
    { src: image9, alt: "Image 9", description: "" }
];
const carouselImagesCompany = [
    { src: image1, alt: "Image 1", description: "" },
    { src: image2, alt: "Image 2", description: "" },
    { src: image3, alt: "Image 3", description: "" },
    { src: image4, alt: "Image 4", description: "" },
    { src: image5, alt: "Image 5", description: "" },
    { src: image6, alt: "Image 6", description: "" },
    { src: image7, alt: "Image 7", description: "" },
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
        <div class="d-flex flex-column w-20 align-center justify-center">
            <v-chip size="x-large" class="my-b" color="primary">
                <h3>{{ t('project.exampleImg') }}</h3>
            </v-chip>
            <v-chip size="small" class="my-2" color="error">* สามารถกดที่รูปเพื่อขยาย</v-chip>
        </div>
        <v-row>
            <v-col cols="12" md="12" class="mt-10">
                <v-row>
                    <v-col cols="12" md="6">
                        <Carousel v-bind="carouselConfig" :autoplay="2000" :interval="3000" :transition="500">
                            <Slide v-for="(item, index) in carouselImagesEcom" :key="index">
                                <div class="carousel__item" @click="openDialog(item.src)">
                                    <img :src="item.src" :alt="item.alt" class="carousel-image" />
                                </div>
                            </Slide>
                            <template #addons>
                                <Navigation />
                                <Pagination />
                            </template>
                        </Carousel>
                        <v-card class="pa-4 rounded-lg mt-5" elevation="3">
                            <v-card-title class="d-flex flex-column flex-sm-row align-sm-center">
                                <span class="kanit-medium ml-sm-2">
                                    {{ t('project.des.e-com.role') }}&nbsp;
                                </span>
                                <span class="kanit-light text-primary text-body-2 ml-sm-2">
                                    Rajamangala University Of Technology Isan
                                </span>
                            </v-card-title>
                            <v-divider></v-divider>
                            <v-card-text style="position: relative;">
                                <div style="position: absolute; top: 5px; left: 5px;">
                                    <span class="text-body-5">
                                        {{ t('project.des.e-com.title') }}
                                    </span>
                                </div>
                                <div class="mt-4">
                                    <p class="kanit-light">
                                        {{ t('project.des.e-com.detail') }}
                                    </p>
                                </div>
                            </v-card-text>
                            <v-card-actions class="d-flex justify-start">
                                <v-btn href="https://github.com/Fexx745/Project-E-Com" target="_blank" variant="text"
                                    class="text-primary">
                                    <v-icon start>mdi-github</v-icon>
                                    GitHub
                                </v-btn>
                            </v-card-actions>
                        </v-card>
                    </v-col>
                    <v-col cols="12" md="6">
                        <Carousel v-bind="carouselConfig" :autoplay="2000" :interval="3000" :transition="500">
                            <Slide v-for="(item, index) in carouselImagesCompany" :key="index">
                                <div class="carousel__item" @click="openDialog(item.src)">
                                    <img :src="item.src" :alt="item.alt" class="carousel-image" />
                                </div>
                            </Slide>
                            <template #addons>
                                <Navigation />
                                <Pagination />
                            </template>
                        </Carousel>
                        <v-card class="pa-4 rounded-lg mt-5" elevation="3">
                            <v-card-title class="d-flex align-center flex-wrap flex-md-nowrap">
                                <div class="d-flex flex-column flex-sm-row align-sm-center">
                                    <span class="kanit-medium ml-sm-2">{{ t('project.des.mytask.role') }}</span>
                                    <span class="kanit-medium text-primary text-body-2 ml-sm-2">Revel Soft</span>
                                </div>
                            </v-card-title>
                            <v-divider></v-divider>
                            <v-card-text style="position: relative;">
                                <div style="position: absolute; top: 5px; left: 5px;">
                                    <span class="text-body-5">
                                        {{ t('project.des.mytask.title') }}
                                    </span>
                                </div>
                                <div class="mt-5">
                                    <p class="kanit-light">
                                        {{ t('project.des.mytask.detail') }}
                                    </p>
                                </div>
                            </v-card-text>
                            <v-card-actions class="d-flex justify-start">
                                <v-btn href="" target="_blank" variant="text" class="text-red">
                                    <v-icon start>mdi-lock</v-icon>
                                    ไม่สามารถเปิดเผยได้
                                </v-btn>
                            </v-card-actions>
                        </v-card>
                    </v-col>
                </v-row>
            </v-col>
        </v-row>
    </v-container>

    <v-dialog v-model="showDialog" max-width="1000">
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
    height: 220px;
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
