<script setup lang="ts">
import { ref } from 'vue';

// Logos des partenaires
const partners = [
    { name: 'D-Link', logo: '/logo/D-Link.png', url: 'https://www.dlink.com' },
    { name: 'Samsung', logo: '/logo/samsung.png', url: 'https://www.samsung.com' },
    { name: 'Schneider Electric', logo: '/logo/schneider-electric-logo.png', url: 'https://www.se.com' },
    { name: 'Alcatel-Lucent', logo: '/logo/Alcatel-Lucent_logo.svg.png', url: 'https://www.al-enterprise.com' },
    { name: 'Hikvision', logo: '/logo/hikvision.png', url: 'https://www.hikvision.com' },
    { name: 'Majorcom', logo: '/logo/majorcom.png', url: 'https://www.majorcom.fr' },
    { name: 'Tyco', logo: '/logo/tyco.png', url: 'https://www.tycosecurity.com' },
];

// Dupliquer pour l'effet infini
const duplicatedPartners = [...partners, ...partners];

const isPaused = ref(false);

const handleMouseEnter = () => {
    isPaused.value = true;
};

const handleMouseLeave = () => {
    isPaused.value = false;
};
</script>

<template>
    <div class="w-full bg-white py-16 lg:py-20">
        <div class="mx-auto max-w-[90%] px-6 lg:px-8">
            <!-- En-tête -->
            <div class="mb-12 text-center">
                <h2 class="mb-4 text-4xl font-bold text-black lg:text-5xl">
                    Ils nous font confiance
                </h2>
                <p class="text-lg text-gray-700">
                    De nombreuses entreprises et institutions aux Antilles-Guyane s'appuient sur notre expertise en téléphonie IP, vidéosurveillance et sécurité électronique.<br />
                    Découvrez nos clients et les projets que nous avons réalisés ensemble.
                </p>
            </div>

            <!-- Carousel Container avec gradient fade -->
            <div class="relative overflow-hidden">
                <!-- Gradient gauche -->
                <div class="pointer-events-none absolute left-0 top-0 z-10 h-full w-32 bg-gradient-to-r from-white to-transparent"></div>
                
                <!-- Gradient droite -->
                <div class="pointer-events-none absolute right-0 top-0 z-10 h-full w-32 bg-gradient-to-l from-white to-transparent"></div>

                <!-- Carousel -->
                <div class="overflow-hidden py-8">
                    <div
                        class="flex gap-8"
                        :class="{ 'carousel-animation': !isPaused, 'carousel-paused': isPaused }"
                    >
                        <a
                            v-for="(partner, index) in duplicatedPartners"
                            :key="`${partner.name}-${index}`"
                            :href="partner.url"
                            target="_blank"
                            rel="noopener noreferrer"
                            class="flex h-32 min-w-[200px] flex-shrink-0 items-center justify-center rounded-lg bg-white p-6"
                            @mouseenter="handleMouseEnter"
                            @mouseleave="handleMouseLeave"
                        >
                            <img 
                                :src="partner.logo" 
                                :alt="partner.name"
                                class="h-full w-full object-contain"
                            />
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
@keyframes scroll {
    0% {
        transform: translateX(0);
    }
    100% {
        transform: translateX(-50%);
    }
}

.carousel-animation {
    animation: scroll 20s linear infinite;
    will-change: transform;
}

.carousel-paused {
    animation-play-state: paused;
}
</style>

