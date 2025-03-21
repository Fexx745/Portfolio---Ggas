<script setup lang="ts">
import { useI18n } from "vue-i18n";
import profileImage from '@/assets/images/profile.jpg';
const { t } = useI18n();
</script>

<template>
    <v-container>
        <v-row>
            <v-col class="d-flex justify-center align-center" cols="12" sm="6" md="6" lg="5">
                <v-avatar size="240">
                    <img :src="profileImage" alt="Profile Picture"
                        style="object-fit: cover; width: 100%; height: 100%;">
                </v-avatar>
            </v-col>
            <v-col cols="12" sm="6" md="6" lg="7">
                <v-card class="elevation-0">
                    <v-card-title>
                        <h1>{{ t('about.title') }}</h1>
                    </v-card-title>
                    <v-card-text>
                        <p class="paragraph">{{ t('about.des') }}</p>
                    </v-card-text>
                </v-card>
            </v-col>
        </v-row>

        <!-- <v-row justify="center">
            <v-col cols="12" md="12" class="text-center">
                <v-card class="pa-5" elevation="0">
                    <v-avatar size="200">
                        <img :src="profileImage" alt="Profile Picture"
                            style="object-fit: cover; width: 100%; height: 100%;">
                    </v-avatar>
                    <h1>{{ t('about.title') }}</h1>
                   
                </v-card>
            </v-col>
        </v-row> -->
    </v-container>
</template>

<style scoped>
h1 {
    text-align: center;
    margin-top: 20px;
    font-size: 2.5em;
    font-weight: bold;
}

p {
    text-align: center;
    margin-top: 10px;
    font-size: 1.2em;
}

.paragraph {
    max-width: 600px;
    margin: 0 auto;
    text-align: justify;
    line-height: 1.6; 
}
</style>