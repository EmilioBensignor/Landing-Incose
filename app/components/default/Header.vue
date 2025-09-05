<template>
    <header class="sticky top-0 z-50 bg-dark/70 shadow-md py-4 lg:py-8 px-5 md:px-12 lg:px-16 xxl:px-20">
        <div class="max-w-[1280px] flex justify-between items-center   mx-auto">
            <NuxtImg src="/images/Logo-Incose.svg" alt="Logo Incose"
                class="w-12 lg:w-20 h-11 lg:h-[4.75rem] object-contain" />
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
        </div>
    </header>
</template>

<script setup>
import redes from '~/shared/redes';
</script>