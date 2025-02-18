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
import image10 from '@/assets/images/caroucel/10.png'
import image11 from '@/assets/images/caroucel/11.png'
import image12 from '@/assets/images/caroucel/12.png'
import image13 from '@/assets/images/caroucel/13.png'
import image14 from '@/assets/images/caroucel/14.png'
import image15 from '@/assets/images/caroucel/15.png'
import image16 from '@/assets/images/caroucel/16.png'
import image17 from '@/assets/images/caroucel/17.png'
import image18 from '@/assets/images/caroucel/18.png'
import image19 from '@/assets/images/caroucel/19.png'
import image20 from '@/assets/images/caroucel/20.png'
import image21 from '@/assets/images/caroucel/21.png'
import image22 from '@/assets/images/caroucel/22.png'
import image23 from '@/assets/images/caroucel/23.png'

const carouselImagesEcom = [
    { src: image8, alt: "Image 8", description: "" },
    { src: image9, alt: "Image 9", description: "" },
    { src: image10, alt: "Image 10", description: "" },
    { src: image11, alt: "Image 11", description: "" },
    { src: image12, alt: "Image 12", description: "" },
    { src: image13, alt: "Image 13", description: "" },
    { src: image14, alt: "Image 14", description: "" },
    { src: image15, alt: "Image 15", description: "" },
    { src: image16, alt: "Image 16", description: "" },
    { src: image17, alt: "Image 17", description: "" },
    { src: image18, alt: "Image 18", description: "" },
    { src: image19, alt: "Image 19", description: "" },
    { src: image20, alt: "Image 20", description: "" },
    { src: image21, alt: "Image 21", description: "" },
    { src: image22, alt: "Image 22", description: "" },
    { src: image23, alt: "Image 23", description: "" }
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
                <h3><v-icon style="margin-top: -5px;">mdi-briefcase-outline</v-icon>&nbsp;{{ t('project.exampleImg') }}
                </h3>
            </v-chip>
        </div>
        <v-row>
            <v-col cols="12" md="12" class="mt-10">
                <v-row>
                    <v-col cols="12" md="6">
                        <Carousel v-bind="carouselConfig" :autoplay="2000" :itemsToShow="1" :interval="3000"
                            :transition="500">
                            <Slide v-for="(item, index) in carouselImagesEcom" :key="index" style="position: relative;">
                                <div class="carousel__item" @click="openDialog(item.src)">
                                    <img :src="item.src" :alt="item.alt" class="carousel-image" />
                                </div>
                                <div style="position: absolute; bottom: 20px; right: 10px;">
                                    <strong style="color: #f44336; font-size: 14px;">*
                                        {{ t('any.openImg') }}
                                    </strong>
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
                                <strong style="font-size: 18px;" class="text-primary ml-sm-2">
                                    <v-icon>mdi-school</v-icon> Rajamangala University Of Technology Isan
                                </strong>
                            </v-card-title>
                            <v-divider></v-divider>
                            <v-card-text style="position: relative;">
                                <div style="position: absolute; top: 5px; left: 5px;">
                                    <span class="text-body-5">
                                        {{ t('project.des.e-com.title') }}
                                    </span>
                                </div>
                                <div class="mt-4">
                                    <p class="kanit-light detailPD">
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
                        <Carousel v-bind="carouselConfig" :autoplay="2000" :itemsToShow="1" :interval="3000"
                            :transition="500">
                            <Slide v-for="(item, index) in carouselImagesCompany" :key="index"
                                style="position: relative;">
                                <div class="carousel__item" @click="openDialog(item.src)">
                                    <img :src="item.src" :alt="item.alt" class="carousel-image" />
                                </div>
                                <div style="position: absolute; bottom: 20px; right: 10px;">
                                    <strong style="color: #f44336; font-size: 14px;">*
                                        {{ t('any.openImg') }}
                                    </strong>
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
                                    <strong style="font-size: 18px;" class="text-primary ml-sm-2">
                                        <v-icon>mdi-office-building</v-icon> Revel Soft
                                    </strong>
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
                                    <p class="kanit-light detailPD">
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

    <v-dialog v-model="showDialog" max-width="1500">
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

.detailPD {
    max-width: 1000px;
    margin: 0 auto;
    text-align: justify;
    line-height: 1.6;
    text-indent: 2em;
}
</style>
