<script setup lang="ts">
import { RouterView } from 'vue-router';

const title = ref("PORTFOLIO");

useHead({
  meta: [{ content: title }],
  titleTemplate: () => {
    return "PORTFOLIO";
  },
  link: [
    { rel: 'icon', href: '@/assets/images/logo/portfolio.png' }
  ]
});
</script>

<template>
  <v-locale-provider>
    <v-app>
      <LayoutFullMain />
      <v-main>
        <v-container fluid class="pa-0">
          <RouterView />
        </v-container>
      </v-main>
      <FooterFullMain />
    </v-app>
  </v-locale-provider>
</template>