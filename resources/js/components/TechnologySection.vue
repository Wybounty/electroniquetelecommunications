<script setup lang="ts">
</script>

<template>
    <div class="w-full flex flex-col items-center justify-center bg-[#DFECF8] py-12 md:py-16 lg:py-20">
        <div class="mx-auto w-full max-w-[95%] md:max-w-[90%] lg:w-7/8 px-4 md:px-6 lg:px-8">
            <div class="grid grid-cols-1 gap-8 md:gap-12 lg:grid-cols-2">
                <!-- Colonne gauche - Texte -->
                <div class="flex flex-col justify-center">
                    <h2 class="mb-4 md:mb-6 text-3xl md:text-4xl font-bold text-black lg:text-5xl leading-tight">
                        La technologie,<br />
                        proche de vous
                    </h2>
                    <p class="mb-4 md:mb-6 text-base md:text-lg lg:text-xl xl:text-2xl leading-relaxed text-gray-700 max-w-[600px]">
                        Basés aux Antilles-Guyane, nous plaçons la proximité et la confiance au cœur de nos services.
                    </p>
                    <p class="mb-6 md:mb-8 text-base md:text-lg lg:text-xl xl:text-2xl leading-relaxed text-gray-700 max-w-[600px]">
                        Notre mission : vous fournir des solutions télécom et sécurité fiables, performantes et adaptées à votre environnement local.
                    </p>
                    <div class="flex flex-col sm:flex-row gap-3 md:gap-4">
                        <a
                            href="/contact"
                            class="inline-block rounded-md border border-gray-300 bg-white px-6 py-3 text-sm font-medium text-black transition-colors hover:bg-gray-50"
                        >
                            Contactez-nous
                        </a>
                        <a
                            href="/devis"
                            class="inline-block rounded-md bg-[#032340] px-6 py-3 text-sm font-medium text-white transition-colors hover:bg-[#04253a]"
                        >
                            Obtenez un devis
                        </a>
                    </div>
                </div>

                <!-- Colonne droite - Grille de cartes -->
                <div class="grid grid-cols-2 gap-3 md:gap-4">
                    <!-- Téléphonie IP -->
                    <a
                        href="/telephonie-ip"
                        class="group relative h-32 md:h-40 lg:h-[200px] overflow-hidden rounded-lg"
                    >
                        <div class="absolute inset-0 bg-[#052C4E] bg-cover bg-center" style="background-image: url('/images/telephoneip.png')">
                            <div class="absolute inset-0 bg-[#052C4E]/80"></div>
                        </div>
                        <div class="relative flex h-full flex-col items-center justify-center p-2 md:p-4 text-center text-white">
                            <h3 class="mb-1 md:mb-2 text-sm md:text-base lg:text-xl font-bold">Téléphonie IP</h3>
                            <p class="text-xs md:text-sm hidden md:block">Consultez nos solutions</p>
                        </div>
                    </a>

                    <!-- Visioconférence -->
                    <a
                        href="/visioconference"
                        class="group relative h-32 md:h-40 lg:h-[200px] overflow-hidden rounded-lg"
                    >
                        <div class="absolute inset-0 bg-[#052C4E] bg-cover bg-center" style="background-image: url('/images/visio.png')">
                            <div class="absolute inset-0 bg-[#052C4E]/80"></div>
                        </div>
                        <div class="relative flex h-full flex-col items-center justify-center p-2 md:p-4 text-center text-white">
                            <h3 class="mb-1 md:mb-2 text-sm md:text-base lg:text-xl font-bold">Visioconférence</h3>
                            <p class="text-xs md:text-sm hidden md:block">Consultez nos solutions</p>
                        </div>
                    </a>

                    <!-- Réseaux & fibre -->
                    <a
                        href="/reseaux-fibre"
                        class="group relative h-32 md:h-40 lg:h-[200px] overflow-hidden rounded-lg"
                    >
                        <div class="absolute inset-0 bg-[#052C4E] bg-cover bg-center" style="background-image: url('/images/reseaux.png')">
                            <div class="absolute inset-0 bg-[#052C4E]/80"></div>
                        </div>
                        <div class="relative flex h-full flex-col items-center justify-center p-2 md:p-4 text-center text-white">
                            <h3 class="mb-1 md:mb-2 text-sm md:text-base lg:text-xl font-bold">Réseaux & fibre</h3>
                            <p class="text-xs md:text-sm hidden md:block">Consultez nos solutions</p>
                        </div>
                    </a>

                    <!-- Système Anti-intrusion -->
                    <a
                        href="/anti-intrusion"
                        class="group relative h-32 md:h-40 lg:h-[200px] overflow-hidden rounded-lg"
                    >
                        <div class="absolute inset-0 bg-[#052C4E] bg-cover bg-center" style="background-image: url('/images/camera.png')">
                            <div class="absolute inset-0 bg-[#052C4E]/80"></div>
                        </div>
                        <div class="relative flex h-full flex-col items-center justify-center p-2 md:p-4 text-center text-white">
                            <h3 class="mb-1 md:mb-2 text-sm md:text-base lg:text-xl font-bold">Système Anti-intrusion</h3>
                            <p class="text-xs md:text-sm hidden md:block">Consultez nos solutions</p>
                        </div>
                    </a>

                    <!-- Vidéo surveillance -->
                    <a
                        href="/video-surveillance"
                        class="group relative h-32 md:h-40 lg:h-[200px] overflow-hidden rounded-lg"
                    >
                        <div class="absolute inset-0 bg-[#052C4E] bg-cover bg-center" style="background-image: url('/images/antiintru.png')">
                            <div class="absolute inset-0 bg-[#052C4E]/80"></div>
                        </div>
                        <div class="relative flex h-full flex-col items-center justify-center p-2 md:p-4 text-center text-white">
                            <h3 class="mb-1 md:mb-2 text-sm md:text-base lg:text-xl font-bold">Vidéo surveillance</h3>
                            <p class="text-xs md:text-sm hidden md:block">Consultez nos solutions</p>
                        </div>
                    </a>

                    <!-- Studio d'enregistrement -->
                    <a
                        href="/studio-enregistrement"
                        class="group relative h-32 md:h-40 lg:h-[200px] overflow-hidden rounded-lg"
                    >
                        <div class="absolute inset-0 bg-[#052C4E] bg-cover bg-center" style="background-image: url('/images/stud.png')">
                            <div class="absolute inset-0 bg-[#052C4E]/80"></div>
                        </div>
                        <div class="relative flex h-full flex-col items-center justify-center p-2 md:p-4 text-center text-white">
                            <h3 class="mb-1 md:mb-2 text-sm md:text-base lg:text-xl font-bold">Studio d'enregistrement</h3>
                            <p class="text-xs md:text-sm hidden md:block">Consultez nos solutions</p>
                        </div>
                    </a>
                </div>
            </div>
        </div>
    </div>
</template>

