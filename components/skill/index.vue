<script setup lang="ts">
import { useI18n } from "vue-i18n";
const { t } = useI18n();

const ProgrammingLanguages = [
    { name: "HTML", imgUrl: "https://images.vexels.com/media/users/3/166383/isolated/preview/6024bc5746d7436c727825dc4fc23c22-html-programming-language-icon.png" },
    { name: "CSS", imgUrl: "https://www.svgrepo.com/show/353623/css-3.svg" },
    { name: "JavaScript", imgUrl: "https://img.icons8.com/color/512/javascript.png" },
    { name: "TypeScript", imgUrl: "https://cdn-icons-png.flaticon.com/512/5968/5968381.png" },
    { name: "PHP", imgUrl: "https://cdn-icons-png.flaticon.com/512/5968/5968332.png" },
    { name: "Node.js", imgUrl: "https://img.icons8.com/color/512/nodejs.png" },
    { name: "SQL", imgUrl: "https://cdn-icons-png.flaticon.com/512/4299/4299956.png" },
    { name: "Dart", imgUrl: "https://static-00.iconduck.com/assets.00/dart-icon-511x512-jhyea1ft.png" },
];

const Frameworks = [
    { name: "Bootstrap", imgUrl: "https://cdn-icons-png.flaticon.com/512/5968/5968672.png" },
    { name: "Tailwind CSS", imgUrl: "https://upload.wikimedia.org/wikipedia/commons/thumb/d/d5/Tailwind_CSS_Logo.svg/2560px-Tailwind_CSS_Logo.svg.png" },
    { name: "Vuetify", imgUrl: "https://cdn.vuetifyjs.com/images/logos/logo.svg" },
    { name: "React", imgUrl: "https://cdn4.iconfinder.com/data/icons/logos-3/600/React.js_logo-512.png" },
    { name: "Next.js", imgUrl: "https://static-00.iconduck.com/assets.00/next-js-icon-2048x2048-5dqjgeku.png" },
    { name: "Vue.js", imgUrl: "https://upload.wikimedia.org/wikipedia/commons/thumb/9/95/Vue.js_Logo_2.svg/1200px-Vue.js_Logo_2.svg.png" },
    { name: "NuxtJS", imgUrl: "https://nuxt.com/assets/design-kit/icon-green.svg" },
    { name: "Flutter", imgUrl: "https://cdn.iconscout.com/icon/free/png-256/free-flutter-logo-icon-download-in-svg-png-gif-file-formats--programming-language-coding-development-logos-icons-1720090.png?f=webp" }
];

const Tools = [
    { name: "VS Code", imgUrl: "https://upload.wikimedia.org/wikipedia/commons/thumb/9/9a/Visual_Studio_Code_1.35_icon.svg/2048px-Visual_Studio_Code_1.35_icon.svg.png" },
    { name: "Postman", imgUrl: "https://cdn.iconscout.com/icon/free/png-256/free-postman-logo-icon-download-in-svg-png-gif-file-formats--technology-social-media-company-brand-vol-5-pack-logos-icons-2945092.png?f=webp&w=256" },
    { name: "GitHub Desktop", imgUrl: "https://upload.wikimedia.org/wikipedia/commons/thumb/a/ae/Github-desktop-logo-symbol.svg/2048px-Github-desktop-logo-symbol.svg.png" },
    { name: "Figma", imgUrl: "https://upload.wikimedia.org/wikipedia/commons/thumb/3/33/Figma-logo.svg/1200px-Figma-logo.svg.png" },
    { name: "MySQL Workbench", imgUrl: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRBZ2GT4L-Gov2eodIbKZrVx4twV0HRVVfRjA&s" },
    { name: "MongoDB", imgUrl: "https://svgmix.com/uploads/skillicons/5c80e9-mongodb.svg" },
];


</script>

<template>
    <v-container>
        <v-row>
            <v-col cols="12" md="4">
                <v-card class="pa-4 box-item" elevation="5" rounded>
                    <v-card-title class="headline text-center">
                        <v-chip size="x-large" color="info" class="mb-3"> 
                            <h3>{{ t('skill.programming_languages') }}</h3>
                        </v-chip> 
                    </v-card-title>
                    <v-divider></v-divider>
                    <v-card-text>
                        <v-row>
                            <v-col v-for="language in ProgrammingLanguages" :key="language.name" cols="6" sm="6" md="4">
                                <div :title="language.name" class="d-flex align-center mb-2 flex-column hover-effect"
                                    style="padding: 20px; border: 1px solid #ccc; border-radius: 8px;">
                                    <img :src="language.imgUrl" :alt="language.name"
                                        style="width: 70px; height: 70px; object-fit: cover;">
                                    <span>{{ language.name }}</span>
                                </div>
                            </v-col>
                        </v-row>
                    </v-card-text>
                </v-card>
            </v-col>
            <v-col cols="12" md="4">
                <v-card class="pa-4 box-item" elevation="5" rounded>
                    <v-card-title class="headline text-center">
                        <v-chip size="x-large" color="info" class="mb-3"> 
                            <h3>{{ t('skill.frameworks') }}</h3>
                        </v-chip>
                    </v-card-title>
                    <v-divider></v-divider>
                    <v-card-text>
                        <v-row>
                            <v-col v-for="framework in Frameworks" :key="framework.name" cols="6" sm="6" md="4">
                                <div :title="framework.name" class="d-flex align-center mb-2 flex-column hover-effect"
                                    style="padding: 20px; border: 1px solid #ccc; border-radius: 8px;">
                                    <img :src="framework.imgUrl" :alt="framework.name"
                                        style="width: 70px; height: 70px; object-fit: cover;">
                                    <span>{{ framework.name }}</span>
                                </div>
                            </v-col>
                        </v-row>
                    </v-card-text>
                </v-card>
            </v-col>
            <v-col cols="12" md="4">
                <v-card class="pa-4 box-item" elevation="5" rounded>
                    <v-card-title class="headline text-center">
                        <v-chip size="x-large" color="info" class="mb-3"> 
                            <h3>{{ t('skill.tools') }}</h3>
                        </v-chip>
                    </v-card-title>
                    <v-divider></v-divider>
                    <v-card-text>
                        <v-row>
                            <v-col v-for="tool in Tools" :key="tool.name" cols="6" sm="6" md="4">
                                <div :title="tool.name" class="d-flex align-center mb-2 flex-column hover-effect"
                                    style="padding: 20px; border: 1px solid #ccc; border-radius: 8px;">
                                    <img :src="tool.imgUrl" :alt="tool.name"
                                        style="width: 70px; height: 70px; object-fit: cover;">
                                    <span>{{ tool.name }}</span>
                                </div>
                            </v-col>
                        </v-row>
                    </v-card-text>
                </v-card>
            </v-col>
        </v-row>
    </v-container>
</template>

<style scoped>
.hover-effect {
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.hover-effect:hover {
    transform: scale(1.05);
    transition: transform 0.3s ease-in-out;
    background-color: rgb(95, 94, 94);
    color: #fff;
    cursor: pointer;
}

.v-card-title {
    font-weight: bold;
}

.box-item {
    flex: 1 1 auto;
    height: 100%;
}
</style>
