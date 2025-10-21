<script setup lang="ts">
import PublicHeader from '@/components/PublicHeader.vue';
import PublicFooter from '@/components/PublicFooter.vue';
import FirstContact from '@/components/FirstContact.vue';
import ServicesSection from '@/components/ServicesSection.vue';
import TechnologySection from '@/components/TechnologySection.vue';
import BlogSection from '@/components/BlogSection.vue';
import ExpertContactSection from '@/components/ExpertContactSection.vue';
import TrustCarousel from '@/components/TrustCarousel.vue';
import HeroCarousel from '@/components/HeroCarousel.vue';
import { Head } from '@inertiajs/vue3';

withDefaults(
    defineProps<{
        canRegister: boolean;
    }>(),
    {
        canRegister: true,
    },
);
</script>

<template>
    <Head title="Welcome">
        <link rel="preconnect" href="https://rsms.me/" />
        <link rel="stylesheet" href="https://rsms.me/inter/inter.css" />
    </Head>
    <div class="flex min-h-screen flex-col bg-[#FDFDFC] text-[#1b1b18] dark:bg-[#0a0a0a]">
        <PublicHeader :can-register="canRegister" />
        
        <main class="w-full flex-1">
            
            <!-- Hero Carousel -->
            <HeroCarousel />

            <!-- Trust Carousel -->
            <TrustCarousel />
            
            <!-- Technology Section -->
            <TechnologySection />
            
            <!-- Section des services -->
            <ServicesSection />
            
            <!-- Expert Contact Section -->
            <ExpertContactSection />

            <!-- Blog Section -->
            <BlogSection />

            <!-- First Contact -->
            <FirstContact />
            
            </main>
        <PublicFooter />
    </div>
</template>
