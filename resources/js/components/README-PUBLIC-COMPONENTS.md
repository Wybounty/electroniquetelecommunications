# Composants Publics

Ce document décrit l'utilisation des composants Header et Footer pour les pages publiques de votre application.

## Composants disponibles

### 1. PublicHeader

Un composant header moderne avec navigation et authentification intégrée.

**Emplacement :** `resources/js/components/PublicHeader.vue`

**Props :**
- `canRegister` (optionnel, boolean, défaut: `true`) - Affiche ou cache le bouton d'inscription

**Caractéristiques :**
- Mode clair/sombre automatique
- Navigation responsive
- Liens vers Dashboard (si authentifié) ou Login/Register
- Design moderne avec effet backdrop-blur

**Exemple d'utilisation :**
```vue
<script setup lang="ts">
import PublicHeader from '@/components/PublicHeader.vue';
</script>

<template>
    <PublicHeader :can-register="true" />
</template>
```

### 2. PublicFooter

Un composant footer complet avec liens, informations légales et réseaux sociaux.

**Emplacement :** `resources/js/components/PublicFooter.vue`

**Caractéristiques :**
- 4 colonnes de liens (À propos, Liens rapides, Ressources, Légal)
- Section copyright avec année dynamique
- Icônes de réseaux sociaux (GitHub, Twitter/X, LinkedIn)
- Design responsive

**Exemple d'utilisation :**
```vue
<script setup lang="ts">
import PublicFooter from '@/components/PublicFooter.vue';
</script>

<template>
    <PublicFooter />
</template>
```

### 3. PublicLayout

Un layout réutilisable qui combine Header et Footer pour faciliter la création de pages publiques.

**Emplacement :** `resources/js/layouts/PublicLayout.vue`

**Props :**
- `canRegister` (optionnel, boolean, défaut: `true`) - Passé au composant PublicHeader

**Caractéristiques :**
- Structure complète avec Header, contenu principal (slot) et Footer
- Gestion automatique du min-height
- Styles cohérents pour mode clair/sombre

**Exemple d'utilisation :**
```vue
<script setup lang="ts">
import PublicLayout from '@/layouts/PublicLayout.vue';
import { Head } from '@inertiajs/vue3';
</script>

<template>
    <PublicLayout :can-register="true">
        <Head title="Ma page" />
        
        <div class="mx-auto max-w-7xl px-6 py-12 lg:px-8">
            <h1>Mon contenu</h1>
            <!-- Votre contenu ici -->
        </div>
    </PublicLayout>
</template>
```

## Utilisation recommandée

### Méthode 1 : Utiliser le PublicLayout (Recommandé)

Cette méthode est la plus simple et la plus propre :

```vue
<script setup lang="ts">
import PublicLayout from '@/layouts/PublicLayout.vue';
import { Head } from '@inertiajs/vue3';
</script>

<template>
    <PublicLayout>
        <Head title="Ma page" />
        
        <!-- Votre contenu ici -->
        <div class="container mx-auto py-8">
            <h1>Titre de ma page</h1>
            <p>Contenu de ma page</p>
        </div>
    </PublicLayout>
</template>
```

### Méthode 2 : Utiliser les composants séparément

Si vous avez besoin de plus de contrôle sur la structure :

```vue
<script setup lang="ts">
import PublicHeader from '@/components/PublicHeader.vue';
import PublicFooter from '@/components/PublicFooter.vue';
import { Head } from '@inertiajs/vue3';
</script>

<template>
    <Head title="Ma page" />
    
    <div class="flex min-h-screen flex-col">
        <PublicHeader :can-register="true" />
        
        <main class="flex-1">
            <!-- Votre contenu ici -->
        </main>
        
        <PublicFooter />
    </div>
</template>
```

## Personnalisation

### Modifier les liens du Header

Éditez `resources/js/components/PublicHeader.vue` pour ajouter ou modifier les liens de navigation.

### Modifier les liens du Footer

Éditez `resources/js/components/PublicFooter.vue` pour personnaliser :
- Les colonnes de liens
- Les icônes de réseaux sociaux
- Le texte de copyright
- Les sections du footer

### Styles

Les composants utilisent les classes Tailwind CSS cohérentes avec le design de l'application :
- Couleurs principales : `#1b1b18` (texte), `#f53003` (accent clair), `#FF4433` (accent sombre)
- Bordures : `border-[#19140035]` (clair), `border-[#3E3E3A]` (sombre)
- Support du mode sombre avec la classe `dark:`

## Exemple complet

Voir `resources/js/pages/ExemplePublic.vue` pour un exemple complet d'utilisation avec :
- Hero section
- Grid de fonctionnalités
- Call-to-action
- Mise en page responsive

## Migration de pages existantes

Pour migrer une page existante (comme Welcome.vue) :

1. Importez les composants :
```typescript
import PublicHeader from '@/components/PublicHeader.vue';
import PublicFooter from '@/components/PublicFooter.vue';
```

2. Remplacez votre header existant par `<PublicHeader />`

3. Ajoutez `<PublicFooter />` avant la fermeture du div principal

4. Ajustez la structure pour utiliser flexbox :
```html
<div class="flex min-h-screen flex-col">
    <PublicHeader />
    <main class="flex-1">
        <!-- Contenu -->
    </main>
    <PublicFooter />
</div>
```

