<script setup lang="ts">
import { Head } from '@inertiajs/vue3';
import PublicHeader from '@/components/PublicHeader.vue';
import PublicFooter from '@/components/PublicFooter.vue';
import FirstContact from '@/components/FirstContact.vue';
import ExpertContactSection from '@/components/ExpertContactSection.vue';
import { ref } from 'vue';

withDefaults(
    defineProps<{
        canRegister: boolean;
    }>(),
    {
        canRegister: true,
    },
);

const form = ref({
    nom: '',
    prenom: '',
    email: '',
    objet: '',
    telephone: '',
    services: [] as string[],
    demande: '',
    accepteConfidentialite: false,
});

const handleSubmit = () => {
    // Logic pour envoyer le formulaire
    console.log('Formulaire soumis:', form.value);
};
</script>

<template>
    <Head title="Obtenir un devis">
        <link rel="preconnect" href="https://rsms.me/" />
        <link rel="stylesheet" href="https://rsms.me/inter/inter.css" />
    </Head>
    <div class="flex min-h-screen flex-col bg-white text-[#1b1b18]">
        <PublicHeader :can-register="canRegister" />
        
        <main class="w-full flex-1">
            <!-- Section Formulaire de devis -->
            <div class="w-full bg-white py-12 md:py-16 lg:py-20">
                <div class="mx-auto w-full max-w-[95%] md:max-w-[90%] lg:max-w-[1200px] px-4 md:px-6 lg:px-8">
                    <!-- En-tête -->
                    <div class="mb-8 md:mb-12 text-center">
                        <h1 class="mb-4 md:mb-6 text-3xl md:text-4xl font-bold text-black lg:text-5xl">
                            Obtenir un devis
                        </h1>
                        <p class="mx-auto max-w-3xl text-sm md:text-base text-gray-700 leading-relaxed">
                            Obtenez rapidement une estimation claire et sans engagement.<br />
                            Notre équipe analyse vos besoins pour vous proposer, sous quelques jours, la solution IT la plus efficace et économique.
                        </p>
                    </div>

                    <!-- Formulaire -->
                    <div class="mx-auto max-w-4xl rounded-2xl bg-[#cddce9] p-6 md:p-8 lg:p-12">
                        <form @submit.prevent="handleSubmit" class="space-y-6">
                            <!-- Nom et Prénom -->
                            <div class="grid grid-cols-1 gap-4 md:grid-cols-2">
                                <div>
                                    <input
                                        v-model="form.nom"
                                        type="text"
                                        placeholder="Votre nom"
                                        required
                                        class="w-full rounded-md border-0 bg-white px-4 py-3 text-sm text-gray-900 placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-[#032340]"
                                    />
                                </div>
                                <div>
                                    <input
                                        v-model="form.prenom"
                                        type="text"
                                        placeholder="Votre prénom"
                                        required
                                        class="w-full rounded-md border-0 bg-white px-4 py-3 text-sm text-gray-900 placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-[#032340]"
                                    />
                                </div>
                            </div>

                            <!-- Email -->
                            <div>
                                <input
                                    v-model="form.email"
                                    type="email"
                                    placeholder="Votre email"
                                    required
                                    class="w-full rounded-md border-0 bg-white px-4 py-3 text-sm text-gray-900 placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-[#032340]"
                                />
                            </div>

                            <!-- Objet de la demande -->
                            <div>
                                <input
                                    v-model="form.objet"
                                    type="text"
                                    placeholder="Objet de votre demande"
                                    required
                                    class="w-full rounded-md border-0 bg-white px-4 py-3 text-sm text-gray-900 placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-[#032340]"
                                />
                            </div>

                            <!-- Téléphone -->
                            <div>
                                <input
                                    v-model="form.telephone"
                                    type="tel"
                                    placeholder="Téléphone"
                                    required
                                    class="w-full rounded-md border-0 bg-white px-4 py-3 text-sm text-gray-900 placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-[#032340]"
                                />
                            </div>

                            <!-- Services intéressés -->
                            <div class="bg-white rounded-md p-4 md:p-6">
                                <p class="mb-4 text-sm font-medium text-gray-700">Vous êtes intéressé par :</p>
                                <div class="grid grid-cols-1 gap-3 md:grid-cols-2">
                                    <label class="flex items-center gap-2 cursor-pointer">
                                        <input
                                            v-model="form.services"
                                            type="checkbox"
                                            value="telephonie-ip"
                                            class="h-4 w-4 rounded border-gray-300 text-[#032340] focus:ring-[#032340]"
                                        />
                                        <span class="text-sm text-gray-700">Téléphonie IP</span>
                                    </label>
                                    <label class="flex items-center gap-2 cursor-pointer">
                                        <input
                                            v-model="form.services"
                                            type="checkbox"
                                            value="visioconference"
                                            class="h-4 w-4 rounded border-gray-300 text-[#032340] focus:ring-[#032340]"
                                        />
                                        <span class="text-sm text-gray-700">Visioconférence</span>
                                    </label>
                                    <label class="flex items-center gap-2 cursor-pointer">
                                        <input
                                            v-model="form.services"
                                            type="checkbox"
                                            value="anti-intrusion"
                                            class="h-4 w-4 rounded border-gray-300 text-[#032340] focus:ring-[#032340]"
                                        />
                                        <span class="text-sm text-gray-700">Anti-intrusion</span>
                                    </label>
                                    <label class="flex items-center gap-2 cursor-pointer">
                                        <input
                                            v-model="form.services"
                                            type="checkbox"
                                            value="video-surveillance"
                                            class="h-4 w-4 rounded border-gray-300 text-[#032340] focus:ring-[#032340]"
                                        />
                                        <span class="text-sm text-gray-700">Vidéo surveillance</span>
                                    </label>
                                    <label class="flex items-center gap-2 cursor-pointer">
                                        <input
                                            v-model="form.services"
                                            type="checkbox"
                                            value="reseaux-fibre"
                                            class="h-4 w-4 rounded border-gray-300 text-[#032340] focus:ring-[#032340]"
                                        />
                                        <span class="text-sm text-gray-700">Réseaux & fibre</span>
                                    </label>
                                    <label class="flex items-center gap-2 cursor-pointer">
                                        <input
                                            v-model="form.services"
                                            type="checkbox"
                                            value="studio-enregistrement"
                                            class="h-4 w-4 rounded border-gray-300 text-[#032340] focus:ring-[#032340]"
                                        />
                                        <span class="text-sm text-gray-700">Studio d'enregistrement</span>
                                    </label>
                                </div>
                            </div>

                            <!-- Votre demande -->
                            <div>
                                <textarea
                                    v-model="form.demande"
                                    placeholder="Votre demande"
                                    rows="6"
                                    required
                                    class="w-full rounded-md border-0 bg-white px-4 py-3 text-sm text-gray-900 placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-[#032340] resize-none"
                                ></textarea>
                            </div>

                            <!-- Acceptation de la politique de confidentialité -->
                            <div class="flex items-start gap-3">
                                <input
                                    v-model="form.accepteConfidentialite"
                                    type="checkbox"
                                    required
                                    class="mt-1 h-4 w-4 rounded border-gray-300 text-[#032340] focus:ring-[#032340]"
                                />
                                <label class="text-xs text-gray-600 leading-relaxed">
                                    J'ai lu et j'accepte la politique de confidentialité*
                                </label>
                            </div>

                            <!-- Bouton Envoyer -->
                            <div class="pt-4">
                                <button
                                    type="submit"
                                    class="w-full rounded-lg bg-black px-8 py-3 text-base font-medium text-white transition-colors hover:bg-gray-900"
                                >
                                    Envoyer
                                </button>
                            </div>
                        </form>
                    </div>
                </div>
            </div>

            <!-- Expert Contact Section -->
            <ExpertContactSection />

            <!-- First Contact -->
            <FirstContact />
        </main>
        
        <PublicFooter />
    </div>
</template>

