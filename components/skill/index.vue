<script setup lang="ts">
import { useI18n } from "vue-i18n";
const { t } = useI18n();

const ProgrammingLanguages = [
    { name: "HTML", icon: "mdi-language-html5", color: "orange" },
    { name: "CSS", icon: "mdi-language-css3", color: "blue" },

    { name: "JavaScript", icon: "mdi-language-javascript", color: "yellow" },
    { name: "TypeScript", icon: "mdi-language-typescript", color: "blue" },
    { name: "PHP", icon: "mdi-language-php", color: "purple" },
    { name: "Node.js", icon: "mdi-nodejs", color: "green" },
    { name: "SQL", icon: "mdi-database", color: "green" },
    { name: "Dart", icon: "mdi-code-braces", color: "#0175C2" },
];

const Tools = [
    { name: "VS Code", icon: "mdi-microsoft-visual-studio-code", color: "blue" },
    { name: "Postman", icon: "mdi-api", color: "orange" },
    { name: "GitHub Desktop", icon: "mdi-github", color: "black" },
    { name: "Figma", icon: "mdi-palette", color: "yellow" },
    { name: "MySQL Workbench", icon: "mdi-database", color: "blue" }
];

const Frameworks = [
    { name: "Bootstrap", icon: "mdi-bootstrap", color: "purple" },
    { name: "Tailwind CSS", icon: "mdi-tailwind", color: "blue" },
    { name: "Vuetify", icon: "mdi-vuetify", color: "green" },
    { name: "Vue.js", icon: "mdi-vuejs", color: "green" },
    { name: "Nuxt3", icon: "mdi-nuxt", color: "green" },
    { name: "React", icon: "mdi-react", color: "blue" },
    { name: "Flutter", icon: "mdi-language-kotlin", color: "blue" }
];
</script>

<template>
    <v-container>
        <v-row>
            <v-col cols="12" md="4">
                <v-card class="pa-4 box-item" elevation="5" rounded>
                    <v-card-title class="headline text-center">
                        <v-chip size="x-large" color="#3f51b5" class="mb-3">
                            <h3>{{ t('skill.programming_languages') }}</h3>
                        </v-chip>
                    </v-card-title>
                    <v-divider></v-divider>
                    <v-card-text>
                        <v-row>
                            <v-col v-for="language in ProgrammingLanguages" :key="language.name" cols="6" sm="6" md="4">
                                <div :title="language.name" class="d-flex align-center mb-2 flex-column hover-effect"
                                    style="padding: 20px; border: 1px solid #ccc; border-radius: 8px;">
                                    <v-icon :size="60" :color="language.color" class="mr-3">{{ language.icon }}</v-icon>
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
                        <v-chip size="x-large" color="#3f51b5" class="mb-3">
                            <h3>{{ t('skill.frameworks') }}</h3>
                        </v-chip>
                    </v-card-title>
                    <v-divider></v-divider>
                    <v-card-text>
                        <v-row>
                            <v-col v-for="framework in Frameworks" :key="framework.name" cols="6" sm="6" md="4">
                                <div :title="framework.name" class="d-flex align-center mb-2 flex-column hover-effect"
                                    style="padding: 20px; border: 1px solid #ccc; border-radius: 8px;">
                                    <v-icon :size="60" :color="framework.color" class="mr-3">{{ framework.icon
                                        }}</v-icon>
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
                        <v-chip size="x-large" color="#3f51b5" class="mb-3">
                            <h3>
                                {{ t('skill.tools') }}
                            </h3>
                        </v-chip>
                    </v-card-title>
                    <v-divider></v-divider>
                    <v-card-text>
                        <v-row>
                            <v-col v-for="tool in Tools" :key="tool.name" cols="6" sm="6" md="4">
                                <div :title="tool.name" class="d-flex align-center mb-2 flex-column hover-effect"
                                    style="padding: 20px; border: 1px solid #ccc; border-radius: 8px;">
                                    <v-icon :size="50" :color="tool.color" class="mr-3">{{ tool.icon }}</v-icon>
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
    background-color: rgb(124, 124, 124);
    color: #fff;
}

.v-card-title {
    font-weight: bold;
}

.v-icon {
    font-size: 2rem;
}

.box-item {
    flex: 1 1 auto;
    height: 100%;
}
</style>
