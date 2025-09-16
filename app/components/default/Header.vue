<template>
    <header class="sticky top-0 z-50 bg-dark/70 shadow-md py-4 lg:py-8 px-5 md:px-12 lg:px-16 xxl:px-20">
        <div class="max-w-[1280px] flex justify-between items-center   mx-auto">
            <NuxtLink :to="ROUTE_NAMES.HOME">
                <NuxtImg src="/images/Logo-Incose-Blanco.svg" alt="Logo Incose"
                    class="w-12 lg:w-20 h-11 lg:h-[4.75rem] object-contain" />
            </NuxtLink>
            <nav>
                <ul class="flex items-center gap-3">
                    <li v-for="(red, index) in redes" :key="index">
                        <NuxtLink :to="red.route" class="text-white hover:text-primary transition-colors duration-300" target="_blank" rel="noopener">
                            <Icon :name="`simple-icons:${red.icon}`" class="w-6 h-6" />
                        </NuxtLink>
                    </li>
                </ul>
            </nav>
        </div>
    </header>
</template>

<script setup>
import { ROUTE_NAMES } from '~/constants/ROUTE_NAMES';
import redes from '~/shared/redes';
</script>