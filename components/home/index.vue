<script setup lang="ts">
import { useI18n } from "vue-i18n";
const { t } = useI18n();

</script>

<template>
    <v-container>
        <v-row>
            <v-col>
                <img src="../../assets/img/nontachai.jpg" alt="Nontachai"
                    style="border-radius: 50%; width: 200px; height: 200px; display: block; margin-left: auto; margin-right: auto; margin-top: 20px;">
                <p>{{ t('name') }}</p>
                <span>{{ t('home.description') }}</span>
            </v-col>
        </v-row>
    </v-container>
</template>

<style scoped></style>