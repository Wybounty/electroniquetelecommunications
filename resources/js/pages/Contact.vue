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
    message: '',
    accepteConfidentialite: false,
});

const handleSubmit = () => {
    // Logic pour envoyer le formulaire
    console.log('Formulaire soumis:', form.value);
};
</script>

<template>
    <Head title="Contactez-nous">
        <link rel="preconnect" href="https://rsms.me/" />
        <link rel="stylesheet" href="https://rsms.me/inter/inter.css" />
    </Head>
    <div class="flex min-h-screen flex-col bg-white text-[#1b1b18]">
        <PublicHeader :can-register="canRegister" />
        
        <main class="w-full flex-1">
            <!-- Section Formulaire de contact -->
            <div class="w-full bg-white py-12 md:py-16 lg:py-20">
                <div class="mx-auto w-full max-w-[95%] md:max-w-[90%] lg:max-w-[1200px] px-4 md:px-6 lg:px-8">
                    <!-- En-tête -->
                    <div class="mb-8 md:mb-12 text-center">
                        <h1 class="mb-4 md:mb-6 text-3xl md:text-4xl font-bold text-black lg:text-5xl">
                            Contactez-nous
                        </h1>
                        <p class="mx-auto max-w-3xl text-sm md:text-base text-gray-700 leading-relaxed">
                            Découvrez nos services de télécommunications et sécurité électronique complets,<br />
                            couvrant téléphonie IP, vidéosurveillance, contrôle d'accès, sécurité incendie et alarmes anti-intrusion.
                        </p>
                    </div>

                    <!-- Section principale avec carte et formulaire -->
                    <div class="mx-auto max-w-6xl rounded-2xl bg-gray-100 p-6 md:p-8 lg:p-12">
                        <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 lg:gap-12">
                            <!-- Carte à gauche -->
                            <div class="order-2 lg:order-1">
                                <div class="h-64 md:h-80 lg:h-96 rounded-lg overflow-hidden">
                                    <iframe 
                                        src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d7661.408687506197!2d-61.5612341240981!3d16.235632434960067!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x8c1345d2f7e481f9%3A0xbd43c26d72329511!2sELECTRONIC%20TELECOMMUNICATION!5e0!3m2!1sfr!2sfr!4v1761012030450!5m2!1sfr!2sfr" 
                                        width="100%" 
                                        height="100%" 
                                        style="border:0;" 
                                        allowfullscreen
                                        loading="lazy" 
                                        referrerpolicy="no-referrer-when-downgrade"
                                        class="w-full h-full"
                                    ></iframe>
                                </div>
                            </div>

                            <!-- Formulaire à droite -->
                            <div class="order-1 lg:order-2">
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
                                        <select
                                            v-model="form.objet"
                                            required
                                            class="w-full rounded-md border-0 bg-white px-4 py-3 text-sm text-gray-900 focus:outline-none focus:ring-2 focus:ring-[#032340]"
                                        >
                                            <option value="" disabled>Sélectionnez l'objet de votre demande</option>
                                            <option value="telephonie-ip">Téléphonie IP</option>
                                            <option value="visioconference">Visioconférence</option>
                                            <option value="reseaux-fibre">Réseaux & Fibre optique</option>
                                            <option value="video-surveillance">Vidéo surveillance</option>
                                            <option value="anti-intrusion">Système Anti-intrusion</option>
                                            <option value="studio-enregistrement">Studio d'enregistrement</option>
                                        </select>
                                    </div>

                                    <!-- Message -->
                                    <div>
                                        <textarea
                                            v-model="form.message"
                                            placeholder="Votre message"
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
                                            J'ai lu et j'accepte la politique de confidentialité
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

                        <!-- Informations de contact détaillées -->
                        <div class="mt-8 md:mt-12 grid grid-cols-1 md:grid-cols-2 gap-6 md:gap-8">
                            <!-- Electronic telecommunication -->
                            <div class="bg-white rounded-lg p-4 md:p-6">
                                <h3 class="mb-4 text-lg font-bold text-gray-900">
                                    Electronic telecommunication
                                </h3>
                                <div class="space-y-2 text-base text-gray-700">
                                    <p><span class="font-medium">Adresse :</span></p>
                                    <p class="text-sm">
                                        28 RUE DE LA CHAPELLE - ZONE INDUSTRIELLE DE JARRY<br />
                                        - 97122 BAIE-MAHAULT
                                    </p>
                                    <p><span class="font-medium">Tél :</span> 0590 32 51 50</p>
                                    <p><span class="font-medium">Fax :</span> 0590 26 78 13</p>
                                </div>
                            </div>

                            <!-- Electronic telecommunication studio -->
                            <div class="bg-white rounded-lg p-4 md:p-6">
                                <h3 class="mb-4 text-lg font-bold text-gray-900">
                                    Electronic telecommunication studio
                                </h3>
                                <div class="space-y-2 text-base text-gray-700">
                                    <p><span class="font-medium">Tél :</span> 0590 32 51 50</p>
                                    <p><span class="font-medium">Site web :</span></p>
                                    <a
                                        href="https://www.electronictelecommunication-studio.fr"
                                        class="text-sm text-blue-600 hover:text-blue-800 transition-colors break-all"
                                    >
                                        www.electronictelecommunication-studio.fr
                                    </a>
                                </div>
                            </div>
                        </div>
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
