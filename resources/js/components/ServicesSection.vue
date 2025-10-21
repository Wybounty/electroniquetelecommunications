<script setup lang="ts">
import ServiceCard from '@/components/ServiceCard.vue';
</script>

<template>
    <div class="flex flex-col items-center justify-center mx-auto bg-[#052C4E] px-4 md:px-6 py-12 md:py-16 lg:px-8">
        <div class="flex flex-col md:flex-row gap-4 md:gap-6 justify-center w-full max-w-[95%] md:max-w-[90%] lg:w-7/8">
            <!-- Carte 1 -->
            <ServiceCard
                title="Expertise locale & proximité client"
                description="Implantés aux Antilles-Guyane, nous comprenons vos enjeux et vos contraintes locales.<br><br>Nos équipes réactives et disponibles assurent un accompagnement humain, sans décalage horaire et avec une véritable proximité."
                button-text="En savoir plus"
                button-link="/expertises"
            />

            <!-- Carte 2 -->
            <ServiceCard
                title="Sécurité & fiabilité garanties"
                description="La protection de vos locaux et la continuité de vos services sont notre priorité absolue, aujourd'hui et demain.<br><br>Nos solutions de vidéosurveillance, contrôle d'accès et alarmes anti-intrusion intègrent la surveillance proactive et la conformité aux meilleures normes."
                button-text="Nos solutions"
                button-link="/prestations"
            />

            <!-- Carte 3 -->
            <ServiceCard
                title="Flexibilité & évolutivité"
                description="Que vous soyez une PME ou une collectivité, nos offres s'adaptent à votre rythme.<br><br>Des formules modulables, transparentes et sans surprise, pour des solutions télécoms et sécurité taillées sur mesure."
                button-text="Demander un devis"
                button-link="/devis"
            />
        </div>
    </div>
</template>

