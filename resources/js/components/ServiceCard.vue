<script setup lang="ts">
defineProps<{
    title: string;
    description: string;
    buttonText: string;
    buttonLink?: string;
}>();
</script>

<template>
    <div class="flex flex-col justify-between rounded-lg bg-[#052C4E] p-6 md:p-8 text-white w-full md:max-w-none">
        <div>
            <h3 class="mb-4 md:mb-6 text-lg md:text-xl font-bold">{{ title }}</h3>
            <p class="mb-4 md:mb-6 text-sm md:text-base leading-relaxed" v-html="description"></p>
        </div>
        <div>
            <a
                :href="buttonLink || '#'"
                class="inline-block rounded-md bg-white px-5 md:px-6 py-2 md:py-2.5 text-sm font-medium text-[#032340] transition-colors hover:bg-gray-100"
            >
                {{ buttonText }}
            </a>
        </div>
    </div>
</template>

