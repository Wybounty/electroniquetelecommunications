<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue';

interface Slide {
    id: number;
    title: string;
    subtitle: string;
    buttonText1: string;
    buttonText2: string;
    buttonLink1: string;
    buttonLink2: string;
    backgroundImage: string;
    navLabel: string;
    navLink: string;
}

const slides: Slide[] = [
    {
        id: 1,
        title: 'Votre partenaire IT de confiance en',
        subtitle: 'Martinique, Guadeloupe et Guyane.',
        buttonText1: 'Nos solutions',
        buttonText2: 'Contactez-nous',
        buttonLink1: '/solutions',
        buttonLink2: '/contact',
        backgroundImage: '/images/contact.jpg',
        navLabel: 'Bienvenue',
        navLink: '/bienvenue',
    },
    {
        id: 2,
        title: 'Solutions de téléphonie IP',
        subtitle: 'Communication moderne et fiable pour votre entreprise',
        buttonText1: 'Découvrir',
        buttonText2: 'Contactez-nous',
        buttonLink1: '/telephonie-ip',
        buttonLink2: '/contact',
        backgroundImage: '/images/telephoneip.png',
        navLabel: 'Téléphonie IP',
        navLink: '/telephonie-ip',
    },
    {
        id: 3,
        title: 'Visioconférence professionnelle',
        subtitle: 'Connectez vos équipes partout dans le monde',
        buttonText1: 'En savoir plus',
        buttonText2: 'Contactez-nous',
        buttonLink1: '/visioconference',
        buttonLink2: '/contact',
        backgroundImage: '/images/visio.png',
        navLabel: 'Visioconférence',
        navLink: '/visioconference',
    },
    {
        id: 4,
        title: 'Réseaux & Fibre optique',
        subtitle: 'Infrastructure réseau performante et sécurisée',
        buttonText1: 'Découvrir',
        buttonText2: 'Contactez-nous',
        buttonLink1: '/reseaux-fibre',
        buttonLink2: '/contact',
        backgroundImage: '/images/reseaux.png',
        navLabel: 'Réseaux & fibre',
        navLink: '/reseaux-fibre',
    },
    {
        id: 5,
        title: 'Système Anti-intrusion',
        subtitle: 'Protection avancée pour votre entreprise',
        buttonText1: 'En savoir plus',
        buttonText2: 'Contactez-nous',
        buttonLink1: '/anti-intrusion',
        buttonLink2: '/contact',
        backgroundImage: '/images/antiintru.png',
        navLabel: 'Système Anti-intrusion',
        navLink: '/anti-intrusion',
    },
    {
        id: 6,
        title: 'Vidéo surveillance',
        subtitle: 'Surveillez votre site en temps réel',
        buttonText1: 'Découvrir',
        buttonText2: 'Contactez-nous',
        buttonLink1: '/video-surveillance',
        buttonLink2: '/contact',
        backgroundImage: '/images/camera.png',
        navLabel: 'Vidéo surveillance',
        navLink: '/video-surveillance',
    },
    {
        id: 7,
        title: 'Studio d\'enregistrement',
        subtitle: 'Équipement professionnel pour vos productions',
        buttonText1: 'En savoir plus',
        buttonText2: 'Contactez-nous',
        buttonLink1: '/studio-enregistrement',
        buttonLink2: '/contact',
        backgroundImage: '/images/stud.png',
        navLabel: 'Studio d\'enregistrement',
        navLink: '/studio-enregistrement',
    },
];

const currentSlideIndex = ref(0);
let autoplayInterval: number | null = null;

const goToSlide = (index: number) => {
    currentSlideIndex.value = index;
    resetAutoplay();
};

const nextSlide = () => {
    currentSlideIndex.value = (currentSlideIndex.value + 1) % slides.length;
};

const startAutoplay = () => {
    autoplayInterval = window.setInterval(() => {
        nextSlide();
    }, 5000); // Change toutes les 5 secondes
};

const resetAutoplay = () => {
    if (autoplayInterval !== null) {
        clearInterval(autoplayInterval);
    }
    startAutoplay();
};

onMounted(() => {
    startAutoplay();
});

onUnmounted(() => {
    if (autoplayInterval !== null) {
        clearInterval(autoplayInterval);
    }
});
</script>

<template>
    <div class="relative h-[350px] md:h-[450px] lg:h-[500px] w-full overflow-hidden">
        <!-- Slides avec leur propre background -->
        <div
            v-for="(slide, index) in slides"
            :key="slide.id"
            class="absolute inset-0 transition-opacity duration-1000"
            :class="{
                'opacity-100 z-10': index === currentSlideIndex,
                'opacity-0 z-0': index !== currentSlideIndex,
            }"
        >
            <!-- Background Image de la slide -->
            <div
                class="absolute inset-0 bg-cover bg-center"
                :style="{ backgroundImage: `url('${slide.backgroundImage}')` }"
            >
                <!-- Overlay avec couleur #0558A1 à 70% d'opacité -->
                <div class="absolute inset-0 bg-[#0558A1] opacity-70"></div>
            </div>

            <!-- Content -->
            <div class="relative z-10 flex h-full items-center justify-center">
                <div class="mx-auto max-w-[95%] md:max-w-[90%] px-4 md:px-6 text-center lg:px-8">

                    <!-- Title -->
                    <h1 class="mb-4 text-2xl md:text-3xl lg:text-4xl xl:text-5xl font-bold text-white leading-tight">
                        {{ slide.title }}<br />
                        <span class="font-bold">{{ slide.subtitle }}</span>
                    </h1>

                    <!-- Buttons -->
                    <div class="mt-6 md:mt-8 flex flex-col sm:flex-row flex-wrap justify-center gap-3 md:gap-4">
                        <a
                            :href="slide.buttonLink1"
                            class="rounded-md bg-[#032340] px-6 md:px-8 py-2.5 md:py-3 text-sm md:text-base font-medium text-white transition-colors hover:bg-[#04253a]"
                        >
                            {{ slide.buttonText1 }}
                        </a>
                        <a
                            :href="slide.buttonLink2"
                            class="rounded-md bg-white px-6 md:px-8 py-2.5 md:py-3 text-sm md:text-base font-medium text-[#032340] transition-colors hover:bg-gray-100"
                        >
                            {{ slide.buttonText2 }}
                        </a>
                    </div>
                </div>
            </div>
        </div>

        <!-- Navigation bar en bas -->
        <div class="absolute bottom-0 left-0 right-0 z-20 bg-gray-50 overflow-x-auto">
            <div class="mx-auto flex max-w-full items-center justify-start md:justify-center min-w-max md:min-w-0">
                <a
                    v-for="(slide, index) in slides"
                    :key="`nav-${slide.id}`"
                    :href="slide.navLink"
                    class="flex-shrink-0 px-3 md:px-4 lg:px-6 py-3 md:py-4 text-center text-xs md:text-sm font-medium text-gray-700 transition-colors whitespace-nowrap"
                    :class="{
                        'bg-[#0558A1] text-white': index === currentSlideIndex,
                        'hover:bg-gray-200': index !== currentSlideIndex,
                    }"
                    @click.prevent="goToSlide(index)"
                >
                    {{ slide.navLabel }}
                </a>
            </div>
        </div>
    </div>
</template>

