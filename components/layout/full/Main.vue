<script setup>
import { useI18n } from "vue-i18n";
import { ref, computed } from "vue";

const { t } = useI18n();
const drawer = ref(false);
const fullText = "Portforlio";
const displayText = ref('');

const navbar_items = computed(() => [
    { text: t('about.text'), href: "#about-page", icon: "mdi-home-outline" },
    { text: t('skill.text'), href: "#skill-page", icon: "mdi-star-outline" },
    { text: t('project.text'), href: "#project-page", icon: "mdi-briefcase-outline" },
    { text: t('contact.text'), href: "#contact-page", icon: "mdi-email-outline" },
]);

onMounted(() => {
    let index = 0;
    let deleting = false;

    setInterval(() => {
        if (!deleting) {
            displayText.value = fullText.substring(0, index);
            index++;
            if (index > fullText.length) {
                deleting = true;
                index = fullText.length;
            }
        } else {
            displayText.value = fullText.substring(0, index);
            index--;
            if (index === 0) {
                deleting = false;
            }
        }
    }, 100);
});

</script>

<template>
    <v-app-bar app fixed elevation="4" density="comfortable" class="custom-app-bar">
        <v-row align="center" style="width: 100%;" justify="space-between" class="px-8">
            <!-- ขนาด lg -->
            <v-responsive class="d-flex align-center">
                <div class="typing-container d-none d-md-flex">
                    <span class="text kanit-black">{{ displayText }}</span>
                    <span class="cursor">|</span>
                </div>
                <strong class="text-h6 d-inline d-md-none d-sm-none text-md-body-1 kanit-black">
                    <span class="text kanit-black">{{ displayText }}</span>
                </strong>
            </v-responsive>

            <!-- ขนาด md -->
            <div class="d-none d-md-flex">
                <v-btn v-for="(item, index) in navbar_items" :key="index" :prepend-icon="item.icon" :to="item.href"
                    variant="plain" class="mx-2" @focus="onFocus" @blur="onBlur">
                    <strong>{{ item.text }}</strong>
                </v-btn>
            </div>

            <!-- ขนาด มือถือ -->
            <div class="d-flex align-center">
                <LayoutFullVerticalHeaderLanguageSwitcher />
                <LayoutFullVerticalHeaderThemeSwitcher />
            </div>
            <v-app-bar-nav-icon class="d-md-none" @click="drawer = !drawer"></v-app-bar-nav-icon>
        </v-row>
    </v-app-bar>

    <!-- slide ด้านข้าง -->
    <v-navigation-drawer v-model="drawer" app temporary>
        <v-list>
            <v-list-item v-for="(item, index) in navbar_items" :key="index" :to="item.href">
                <template v-slot:prepend>
                    <v-icon>{{ item.icon }}</v-icon>
                </template>
                <v-list-item-title>{{ item.text }}</v-list-item-title>
            </v-list-item>
        </v-list>
    </v-navigation-drawer>
</template>

<style scoped>
.typing-container {
    font-size: 20px;
    font-weight: bold;
    display: inline-flex;
    align-items: center;
    white-space: nowrap;
}

.text {
    display: inline-block;
}

.cursor {
    display: inline-block;
    width: 10px;
    text-align: center;
    animation: blink 0.6s infinite;
}

@keyframes blink {
    50% {
        opacity: 0;
    }
}
</style>