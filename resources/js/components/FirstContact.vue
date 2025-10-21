<script setup lang="ts">
</script>

<template>
    <div class="w-full bg-black py-8 md:py-12 lg:py-16">
        <div class="mx-auto flex flex-col md:flex-row max-w-[95%] md:max-w-[90%] lg:max-w-7/8 items-center md:items-center justify-between px-4 md:px-6 lg:px-8 gap-6 md:gap-8">
            <!-- Texte et carte à gauche -->
            <div class="flex flex-col items-start gap-4 md:gap-6 w-full md:w-1/2">
                <div>
                    <h1 class="text-2xl md:text-3xl lg:text-4xl font-bold leading-tight text-white">
                        Expert en télécommunications et
                        sécurité électronique en Antilles-Guyane
                    </h1>
                </div>
                
                <!-- Carte des îles -->
                <div class="flex flex-row items-center gap-3 md:gap-4 rounded-lg bg-white p-3 md:p-4">
                    <img src="/images/guadeloupe.png" alt="Guadeloupe" class="w-8 h-8 md:w-10 md:h-10">
                    <img src="/images/martinique.png" alt="Martinique" class="w-8 h-8 md:w-10 md:h-10">
                    <img src="/images/guyane.png" alt="Guyane" class="w-8 h-8 md:w-10 md:h-10">
                </div>
            </div>

            <!-- Bouton à droite -->
            <div class="w-full md:w-auto">
                <a
                    href="/contact"
                    class="block md:inline-block text-center rounded-lg bg-white px-6 md:px-8 py-2.5 md:py-3 text-sm md:text-base font-medium text-black transition-colors hover:bg-gray-100"
                >
                    Contactez un conseiller
                </a>
            </div>
        </div>
    </div>
</template>

