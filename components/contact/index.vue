<script setup lang="ts">
import { useI18n } from "vue-i18n";
const { t } = useI18n();

const contactInfo = [
    { name: "Facebook", icon: "mdi-facebook", link: "https://www.facebook.com/chatupon.singkrajom.2024/", color: "blue" },
    { name: "GitHub", icon: "mdi-github", link: "https://github.com/Fexx745", color: "black" },
    { name: "Line", icon: "mdi-wechat", link: "https://line.me/ti/p/kGgLG4g8PY", color: "green" },
    { name: "Gmail", icon: "mdi-email", link: "mailto:Chatupon21396@gmail.com", color: "red" },
    { name: "Telephone", icon: "mdi-phone", link: "tel:0954699689", color: "warning" }
];
</script>

<template>
    <v-container class="d-flex justify-center flex-column">
        <div class="mb-4">
            <v-chip color="#3f51b5" class="mb-2">
                <h1>{{ t('contact.title') }}</h1>
            </v-chip>

            <p>{{ t('contact.des') }}</p>
        </div>
        <v-row class="justify-center align-center">
            <v-col v-for="item in contactInfo" :key="item.name" cols="12" sm="6" md="2" class="d-flex justify-center">
                <v-btn :href="item.link" target="_blank" fab :color="item.color">
                    <v-icon>{{ item.icon }}</v-icon>&nbsp;
                    <span class="kanit-regular">{{ item.name }}</span>
                </v-btn>
            </v-col>
        </v-row>
    </v-container>
</template>
