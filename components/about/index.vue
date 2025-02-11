<script setup lang="ts">
import { useI18n } from "vue-i18n";
import profileImage from '@/assets/images/profile.jpg';
const { t } = useI18n();
</script>

<template>
    <v-container>
        <v-row justify="center">
            <v-col cols="12" md="12" class="text-center">
                <v-card class="pa-5" elevation="0">
                    <v-avatar size="200">
                        <img :src="profileImage" alt="Profile Picture"
                            style="object-fit: cover; width: 100%; height: 100%;">
                    </v-avatar>
                    <h1>{{ t('about.title') }}</h1>
                    <p>{{ t('about.des') }}</p>
                </v-card>
            </v-col>
        </v-row>
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
</style>