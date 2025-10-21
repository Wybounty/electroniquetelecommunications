<script setup lang="ts">
import { Link } from '@inertiajs/vue3';
</script>

<template>
    <footer class="w-full bg-[#032340] text-white">
        <div class="mx-auto w-full max-w-[95%] md:max-w-[90%] lg:w-7/8 px-4 md:px-6 py-8 md:py-12 lg:px-8">
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-6 gap-6 md:gap-8 lg:gap-4">
                <div class="md:col-span-2 lg:col-span-1">
                    <div class="flex h-[50px] w-[150px] md:h-[60px] md:w-[180px] lg:h-[70px] lg:w-[200px] items-center bg-white">
                        <img
                            src="/logo.png"
                            alt="Logo"
                            class="h-[100px] w-[150px] md:h-[120px] md:w-[180px] lg:h-[150px] lg:w-[200px] object-contain"
                        />
                    </div>
                </div>

                <!-- Plan du site -->
                <div class="lg:col-span-1">
                    <h3 class="mb-3 md:mb-4 text-xs md:text-sm font-bold">Plan du site</h3>
                    <ul class="space-y-1.5 md:space-y-2 text-xs md:text-sm">
                        <li>
                            <Link
                                href="/"
                                class="transition-opacity hover:opacity-80"
                            >
                                > Accueil
                            </Link>
                        </li>
                        <li>
                            <Link
                                href="/expertises"
                                class="transition-opacity hover:opacity-80"
                            >
                                > Expertises
                            </Link>
                        </li>
                        <li>
                            <Link
                                href="/prestations"
                                class="transition-opacity hover:opacity-80"
                            >
                                > Prestations
                            </Link>
                        </li>
                        <li>
                            <Link
                                href="/actualites"
                                class="transition-opacity hover:opacity-80"
                            >
                                > Actualités
                            </Link>
                        </li>
                        <li>
                            <Link
                                href="/notre-histoire"
                                class="transition-opacity hover:opacity-80"
                            >
                                > Notre histoire
                            </Link>
                        </li>
                        <li>
                            <Link
                                href="/contact"
                                class="transition-opacity hover:opacity-80"
                            >
                                > Contact
                            </Link>
                        </li>
                    </ul>
                </div>

                <!-- Zones d'activités -->
                <div class="lg:col-span-1">
                    <h3 class="mb-3 md:mb-4 text-xs md:text-sm font-bold">Zones d'activités</h3>
                    <ul class="space-y-1.5 md:space-y-2 text-xs md:text-sm">
                        <li>> Guadeloupe</li>
                        <li>> Martinique</li>
                        <li>> Guyane</li>
                    </ul>
                </div>

                <!-- Electronic telecommunication -->
                <div class="lg:col-span-1">
                    <h3 class="mb-3 md:mb-4 text-xs md:text-sm font-bold">
                        Electronic telecommunication
                    </h3>
                    <div class="space-y-1.5 md:space-y-2 text-xs md:text-sm">
                        <p>> Adresse :</p>
                        <p class="text-xs">
                            ZI RUE DE LA CHAPELLE - ZONE INDUSTRIELLE DE JARRY<br />
                            -97122 BAIE-MAHAULT
                        </p>
                        <p>> Tél : 0590 32 51 50</p>
                        <p>> Fax : 0590 26 78 13</p>
                    </div>
                </div>

                <!-- Electronic telecommunication studio -->
                <div class="lg:col-span-1">
                    <h3 class="mb-3 md:mb-4 text-xs md:text-sm font-bold">
                        Electronic telecommunication studio
                    </h3>
                    <div class="space-y-1.5 md:space-y-2 text-xs md:text-sm">
                        <p>> Tél : 0590 32 51 50</p>
                        <p>> Site web :</p>
                        <a
                            href="https://www.electronictelecommunication-studio.fr"
                            class="text-xs transition-opacity hover:opacity-80 break-all"
                        >
                            www.electronictelecommunication-studio.fr
                        </a>
                    </div>
                </div>

                <!-- Legals -->
                <div class="lg:col-span-1">
                    <h3 class="mb-3 md:mb-4 text-xs md:text-sm font-bold">Legals</h3>
                    <ul class="space-y-1.5 md:space-y-2 text-xs md:text-sm">
                        <li>
                            <Link
                                href="/politique-confidentialite"
                                class="transition-opacity hover:opacity-80"
                            >
                                > Politique de confidentialité
                            </Link>
                        </li>
                        <li>
                            <Link
                                href="/mentions-legales"
                                class="transition-opacity hover:opacity-80"
                            >
                                > Mentions légales
                            </Link>
                        </li>
                        <li>
                            <Link
                                href="/cgu"
                                class="transition-opacity hover:opacity-80"
                            >
                                > CGU
                            </Link>
                        </li>
                    </ul>
                </div>
            </div>

            <!-- Séparateur -->
            <div class="my-8 border-t border-white/20"></div>

            <!-- Copyright -->
            <div class="text-center">
                <p class="text-sm">
                    Copyright © {{ new Date().getFullYear() }} SMARTCOM360
                </p>
            </div>
        </div>
    </footer>
</template>

