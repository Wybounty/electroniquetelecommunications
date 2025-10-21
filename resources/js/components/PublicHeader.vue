<script setup lang="ts">
import { dashboard, login, register } from '@/routes';
import { Link } from '@inertiajs/vue3';
import { ref } from 'vue';

withDefaults(
    defineProps<{
        canRegister?: boolean;
    }>(),
    {
        canRegister: true,
    },
);

const mobileMenuOpen = ref(false);

const toggleMobileMenu = () => {
    mobileMenuOpen.value = !mobileMenuOpen.value;
};
</script>

<template>
    <header
        class="w-full bg-[#032340] backdrop-blur-sm sticky top-0 z-50"
    >
        <div class="mx-auto flex min-h-20 lg:min-h-28 max-w-[95%] lg:max-w-[90%] items-center px-4 md:px-6 py-3 md:py-4 lg:px-8">
            <nav class="flex h-full w-full items-center justify-between">
                <!-- Logo / Brand -->
                <div class="flex items-center">
                    <Link
                        href="/"
                        class="text-xl font-semibold text-[#1b1b18] dark:text-[#EDEDEC]"
                    >
                    <div class="flex items-center h-[50px] w-[120px] md:h-[60px] md:w-[160px] lg:h-[70px] lg:w-[200px] bg-white">
                        <img src="/logo.png" alt="Logo" class="h-[100px] w-[120px] md:h-[120px] md:w-[160px] lg:h-[150px] lg:w-[200px] object-contain">
                    </div>
                    </Link>
                </div>

                <!-- Mobile Menu Button -->
                <button
                    @click="toggleMobileMenu"
                    class="lg:hidden flex flex-col gap-1 p-2"
                    aria-label="Toggle menu"
                >
                    <span class="block h-0.5 w-6 bg-white transition-all" :class="{ 'rotate-45 translate-y-1.5': mobileMenuOpen }"></span>
                    <span class="block h-0.5 w-6 bg-white transition-all" :class="{ 'opacity-0': mobileMenuOpen }"></span>
                    <span class="block h-0.5 w-6 bg-white transition-all" :class="{ '-rotate-45 -translate-y-1.5': mobileMenuOpen }"></span>
                </button>

                <!-- Navigation Links - Desktop -->
                <ul class="hidden lg:flex items-center gap-4 xl:gap-6 text-sm font-medium text-white">
                    <li>
                        <Link 
                            href="/" 
                            class="transition-colors hover:text-[#f53003] dark:hover:text-[#FF4433]"
                        >
                            Accueil
                        </Link>
                    </li>
                    <li>
                        <Link 
                            href="/expertises" 
                            class="transition-colors hover:text-[#f53003] dark:hover:text-[#FF4433]"
                        >
                            Expertises
                        </Link>
                    </li>
                    <li>
                        <Link 
                            href="/prestations" 
                            class="transition-colors hover:text-[#f53003] dark:hover:text-[#FF4433]"
                        >
                            Prestations
                        </Link>
                    </li>
                    <li>
                        <Link 
                            href="/actualites" 
                            class="transition-colors hover:text-[#f53003] dark:hover:text-[#FF4433]"
                        >
                            Actualités
                        </Link>
                    </li>
                    <li>
                        <Link 
                            href="/notre-histoire" 
                            class="transition-colors hover:text-[#f53003] dark:hover:text-[#FF4433]"
                        >
                            Notre histoire
                        </Link>
                    </li>
                    <li>
                        <Link 
                            href="/contact" 
                            class="transition-colors hover:text-[#f53003] dark:hover:text-[#FF4433]"
                        >
                            Contact
                        </Link>
                    </li>
                </ul>

                <!-- CTA Button - Desktop -->
                <div class="hidden lg:block">
                    <a 
                        href="/devis" 
                        class="flex items-center rounded-lg bg-[#1b1b18] px-4 xl:px-5 py-2 xl:py-3 text-sm font-medium text-white transition-colors hover:bg-black dark:bg-[#eeeeec] dark:text-[#1C1C1A] dark:hover:bg-white whitespace-nowrap"
                    >
                        Obtenir un devis
                    </a>
                </div>
            </nav>
        </div>

        <!-- Mobile Menu -->
        <div 
            v-if="mobileMenuOpen"
            class="lg:hidden bg-[#032340] border-t border-white/10"
        >
            <div class="px-4 py-4 space-y-3">
                <Link 
                    href="/" 
                    class="block py-2 text-sm font-medium text-white transition-colors hover:text-[#FF4433]"
                    @click="toggleMobileMenu"
                >
                    Accueil
                </Link>
                <Link 
                    href="/expertises" 
                    class="block py-2 text-sm font-medium text-white transition-colors hover:text-[#FF4433]"
                    @click="toggleMobileMenu"
                >
                    Expertises
                </Link>
                <Link 
                    href="/prestations" 
                    class="block py-2 text-sm font-medium text-white transition-colors hover:text-[#FF4433]"
                    @click="toggleMobileMenu"
                >
                    Prestations
                </Link>
                <Link 
                    href="/actualites" 
                    class="block py-2 text-sm font-medium text-white transition-colors hover:text-[#FF4433]"
                    @click="toggleMobileMenu"
                >
                    Actualités
                </Link>
                <Link 
                    href="/notre-histoire" 
                    class="block py-2 text-sm font-medium text-white transition-colors hover:text-[#FF4433]"
                    @click="toggleMobileMenu"
                >
                    Notre histoire
                </Link>
                <Link 
                    href="/contact" 
                    class="block py-2 text-sm font-medium text-white transition-colors hover:text-[#FF4433]"
                    @click="toggleMobileMenu"
                >
                    Contact
                </Link>
                <a 
                    href="/devis" 
                    class="block w-full text-center rounded-lg bg-[#1b1b18] px-5 py-3 text-sm font-medium text-white transition-colors hover:bg-black mt-4"
                    @click="toggleMobileMenu"
                >
                    Obtenir un devis
                </a>
            </div>
        </div>
        
        <!-- Contact Bar -->
        <div class="flex justify-center items-center w-full bg-white px-4 py-3 md:py-4 shadow-lg">
            <p class="text-xs md:text-sm text-center"> 
                Contactez un conseiller via <a href="https://wa.me/590325150" class="text-[#15A615] underline font-medium">WhatsApp</a> ou au <a href="tel:0590325150" class="text-blue-500 underline font-medium">0590 32 51 50</a>
            </p>
        </div>
    </header>
</template>

