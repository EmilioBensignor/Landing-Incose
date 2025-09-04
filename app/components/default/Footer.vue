<template>
    <footer class="w-full flex flex-col items-center gap-16 bg-dark text-white py-16 px-5">
        <NuxtImg src="/images/Logo-Incose.svg" alt="Logo Incose" class="w-20 h-[4.75rem] object-contain" />
        <div class="flex flex-col gap-6">
            <ul class="flex flex-col items-center gap-6">
                <li>
                    <NuxtLink :to="`mailto:${ROUTE_NAMES.MAIL}`" class="flex items-center gap-2.5">
                        <Icon name="material-symbols:mail-outline-rounded" class="w-6 h-6 flex-shrink-0" />
                        <p class="underline">{{ ROUTE_NAMES.MAIL }}</p>
                    </NuxtLink>
                </li>
                <li>
                    <NuxtLink :to="`tel:${ROUTE_NAMES.TELEFONO}`" class="flex items-center gap-2.5">
                        <Icon name="material-symbols:call-outline-rounded" class="w-6 h-6 flex-shrink-0" />
                        <p class="underline">{{ ROUTE_NAMES.TELEFONO }}</p>
                    </NuxtLink>
                </li>
            </ul>
            <div class="flex flex-col gap-6 border-t border-white pt-6">
                <nav>
                    <ul class="flex justify-center items-center gap-3">
                        <li v-for="(red, index) in redes" :key="index">
                            <NuxtLink :to="red.route">
                                <NuxtImg :src="`/images/redes/${red.name}.svg`" :alt="`Logo ${red.name}`"
                                    class="w-6 h-6 object-contain" />
                            </NuxtLink>
                        </li>
                    </ul>
                </nav>
                <p class="text-center text-sm">Copyright © 2025 | Desarrollado por Benteveo</p>
            </div>
        </div>
    </footer>
</template>

<script setup>
import { ROUTE_NAMES } from '~/constants/ROUTE_NAMES';
import redes from '~/shared/redes';
</script>