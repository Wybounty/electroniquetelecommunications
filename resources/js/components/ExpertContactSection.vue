<script setup lang="ts">
</script>

<template>
    <div class="w-full">
        <div class="mx-auto">
            <div class="grid grid-cols-1 gap-0 md:grid-cols-2">
                <!-- Image à gauche -->
                <div class="overflow-hidden h-64 md:h-auto">
                    <img
                        src="/images/contact.jpg"
                        alt="Expert Contact"
                        class="h-full w-full object-cover"
                    />
                </div>

                <!-- Contenu à droite avec fond orange -->
                <div class="flex flex-col justify-center bg-[#EEA411] p-8 md:p-12 lg:p-16">
                    <!-- Section 1: Échangez avec un expert -->
                    <div class="mb-8 md:mb-12">
                        <h2 class="mb-4 md:mb-6 text-2xl md:text-3xl font-bold text-white lg:text-4xl">
                            Échangez avec un expert
                        </h2>
                        <p class="mb-4 md:mb-6 text-sm md:text-base leading-relaxed text-white">
                            Nos conseillers aux Antilles-Guyane sont là pour comprendre vos enjeux et vous
                            guider vers la meilleure solution.
                            Un accompagnement personnalisé pour moderniser et sécuriser votre
                            système d'information.
                        </p>
                        <a
                            href="/contact"
                            class="inline-block rounded-md bg-white px-6 md:px-8 py-2.5 md:py-3 text-sm md:text-base font-medium text-[#032340] transition-colors hover:bg-gray-100"
                        >
                            Contactez-nous
                        </a>
                    </div>

                    <!-- Section 2: Obtenez votre devis personnalisé -->
                    <div>
                        <h2 class="mb-4 md:mb-6 text-2xl md:text-3xl font-bold text-white lg:text-4xl">
                            Obtenez votre devis personnalisé
                        </h2>
                        <p class="mb-3 md:mb-4 text-sm md:text-base leading-relaxed text-white">
                            Dites-nous vos besoins : téléphonie IP, vidéosurveillance, contrôle d'accès ou systèmes de sécurité.
                        </p>
                        <p class="mb-4 md:mb-6 text-sm md:text-base leading-relaxed text-white">
                            Nous vous préparons un devis clair et adapté à votre infrastructure, avec un tarif
                            mensuel flexible et sans surprise.
                        </p>
                        <a
                            href="/devis"
                            class="inline-block rounded-md bg-[#032340] px-6 md:px-8 py-2.5 md:py-3 text-sm md:text-base font-medium text-white transition-colors hover:bg-[#04253a]"
                        >
                            Obtenir un devis
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

