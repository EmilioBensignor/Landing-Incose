<template>
    <header class="flex justify-between items-center sticky top-0 z-50 bg-dark shadow-md py-4 px-5">
        <NuxtImg src="/images/Logo-Incose.svg" alt="Logo Incose" class="w-12 h-11 object-contain" />
        <nav>
            <ul class="flex items-center gap-3">
                <li v-for="(red, index) in redes" :key="index">
                    <NuxtLink :to="red.route">
                        <NuxtImg :src="`/images/redes/${red.name}.svg`" :alt="`Logo ${red.name}`"
                            class="w-6 h-6 object-contain" />
                    </NuxtLink>
                </li>
            </ul>
        </nav>
    </header>
</template>

<script setup>
import redes from '~/shared/redes';
</script>