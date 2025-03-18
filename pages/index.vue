<script setup lang="ts">
import { useI18n } from "vue-i18n";
import 'animate.css'; 
</script>

<template>
    <div>
        <section id="about-page" class="animate__animated animate__fadeInDown">
            <div class="section about">
                <About />
            </div>
        </section>
        <section id="skill-page" class="animate__animated animate__fadeInDown">
            <div class="section skill">
                <Skill />
            </div>
        </section>
        <section id="project-page" class="animate__animated animate__fadeInDown">
            <div class="section project">
                <Project />
            </div>
        </section>
        <section id="contact-page" class="animate__animated animate__fadeInDown">
            <div class="section contact">
                <Contact />
            </div>
        </section>
    </div>
</template>

<style scoped>
.animate__animated.animate__fadeInDown {
    --animate-duration: 1.5s;
    --animate-delay: 0.9s;
}

h1,
h2 {
    color: #333;
    margin-bottom: 20px;
    text-align: center;
}

p {
    font-size: 18px;
    color: #555;
    text-align: center;
}

.section {
    height: auto;
    width: 100%;
    padding: 50px 20px 50px 20px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    overflow: hidden;
}
</style>
