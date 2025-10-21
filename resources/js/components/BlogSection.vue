<script setup lang="ts">
</script>

<template>
    <div class="flex flex-col justify-center w-full bg-[#DFECF8] py-16 lg:py-20">
        <div class="mx-auto max-w-7/8 px-6 lg:px-8">
            <!-- Titre et description -->
            <div class="mb-8 md:mb-12 text-center">
                <h2 class="mb-4 md:mb-6 text-3xl md:text-4xl font-bold text-black">
                    Conseils et actualités IT
                </h2>
                <p class="mx-auto max-w-4xl text-sm md:text-base leading-relaxed text-gray-700">
                    Restez informé des dernières tendances technologiques : sécurité des données, infrastructures réseau, téléphonie IP
                    et systèmes de surveillance. Nos articles vous aident à mieux comprendre les enjeux du numérique dans les Antilles-Guyane.
                </p>
            </div>

            <!-- Grille d'articles -->
            <div class="flex flex-col md:flex-row justify-between items-stretch w-full mb-8 md:mb-12 gap-6 md:gap-8">
                <!-- Article 1 - Thème Bleu -->
                <article class="overflow-hidden rounded-lg shadow-lg max-w-[400px] bg-gradient-to-br from-blue-50 to-blue-100 border-2 border-blue-200">
                    <div class="h-48 overflow-hidden relative">
                        <img
                            src="/images/telephonie.jpg"
                            alt="Téléphonie IP en Guadeloupe"
                            class="h-full w-full object-cover"
                        />
                        <div class="absolute top-3 right-3 bg-blue-600 text-white px-3 py-1 rounded-full text-xs font-bold">
                            Téléphonie IP
                        </div>
                    </div>
                    <div class="p-4 md:p-6">
                        <h3 class="mb-2 md:mb-3 text-base md:text-lg font-bold text-blue-900">
                            Téléphonie IP aux Antilles : modernisez
                            votre communication d'entreprise
                        </h3>
                        <p class="mb-3 md:mb-4 text-xs md:text-sm leading-relaxed text-blue-800">
                            La téléphonie IP révolutionne la communication
                            des entreprises. Découvrez comment optimiser
                            vos échanges professionnels
                        </p>
                        <div class="flex flex-col md:flex-row items-start md:items-center justify-between gap-2">
                            <a
                                href="/blog/telephonie-ip-guadeloupe"
                                class="cursor-pointer text-xs md:text-sm font-bold text-blue-600 hover:text-blue-800 transition-colors flex items-center gap-1"
                            >
                                Lire l'article →
                            </a>
                            <span class="text-xs md:text-sm text-blue-600 font-medium">20/20/2025</span>
                        </div>
                    </div>
                </article>

                <!-- Article 2 - Thème Vert -->
                <article class="overflow-hidden rounded-lg shadow-lg max-w-[400px] bg-gradient-to-br from-green-50 to-green-100 border-2 border-green-200">
                    <div class="h-48 overflow-hidden relative">
                        <img
                            src="/images/cybersecurite.jpg"
                            alt="Sécurité digitale"
                            class="h-full w-full object-cover"
                        />
                        <div class="absolute top-3 right-3 bg-green-600 text-white px-3 py-1 rounded-full text-xs font-bold">
                            Sécurité
                        </div>
                    </div>
                    <div class="p-4 md:p-6">
                        <h3 class="mb-2 md:mb-3 text-base md:text-lg font-bold text-green-900">
                            Sécurité digitale aux Antilles-Guyane :
                            Protéger votre infrastructure IT
                        </h3>
                        <p class="mb-3 md:mb-4 text-xs md:text-sm leading-relaxed text-green-800">
                            Face aux menaces croissantes, découvrez
                            comment sécuriser efficacement vos systèmes
                            et protéger vos données sensibles
                        </p>
                        <div class="flex flex-col md:flex-row items-start md:items-center justify-between gap-2">
                            <a
                                href="/blog/migration-cloud-guadeloupe-2"
                                class="cursor-pointer text-xs md:text-sm font-bold text-green-600 hover:text-green-800 transition-colors flex items-center gap-1"
                            >
                                Lire l'article →
                            </a>
                            <span class="text-xs md:text-sm text-green-600 font-medium">20/20/2025</span>
                        </div>
                    </div>
                </article>

                <!-- Article 3 - Thème Orange -->
                <article class="overflow-hidden rounded-lg shadow-lg max-w-[400px] bg-gradient-to-br from-orange-50 to-orange-100 border-2 border-orange-200">
                    <div class="h-48 overflow-hidden relative">
                        <img
                            src="/images/fibre.jpg"
                            alt="Infrastructure réseau"
                            class="h-full w-full object-cover"
                        />
                        <div class="absolute top-3 right-3 bg-orange-600 text-white px-3 py-1 rounded-full text-xs font-bold">
                            Réseau
                        </div>
                    </div>
                    <div class="p-4 md:p-6">
                        <h3 class="mb-2 md:mb-3 text-base md:text-lg font-bold text-orange-900">
                            Optimisation des réseaux en Guyane :
                            défis et solutions
                        </h3>
                        <p class="mb-3 md:mb-4 text-xs md:text-sm leading-relaxed text-orange-800">
                            Comment améliorer la performance de vos
                            infrastructures réseau dans un environnement
                            complexe et exigeant
                        </p>
                        <div class="flex flex-col md:flex-row items-start md:items-center justify-between gap-2">
                            <a
                                href="/blog/migration-cloud-guadeloupe-3"
                                class="cursor-pointer text-xs md:text-sm font-bold text-orange-600 hover:text-orange-800 transition-colors flex items-center gap-1"
                            >
                                Lire l'article →
                            </a>
                            <span class="text-xs md:text-sm text-orange-600 font-medium">20/20/2025</span>
                        </div>
                    </div>
                </article>
            </div>

            <!-- Bouton CTA -->
            <div class="text-center">
                <a
                    href="/devis"
                    class="inline-block rounded-lg bg-[#032340] px-6 md:px-8 py-2.5 md:py-3 text-sm md:text-base font-medium text-white transition-colors hover:bg-[#04253a]"
                >
                    Générer un devis
                </a>
            </div>
        </div>
    </div>
</template>

