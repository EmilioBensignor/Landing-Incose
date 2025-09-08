<template>
    <NuxtLink :to="`${ROUTE_NAMES.ARTICULOS}/${post.slug}`" class="flex flex-col border border-dark">
        <NuxtImg :src="post.img" :alt="post.titulo" class="w-full h-44 object-cover" />
        <div class="flex flex-col gap-2 p-3 lg:py-9 lg:px-6">
            <p class="text-sm font-semibold">{{ post.categoria }}</p>
            <p class="text-xl xxl:text-2xl font-bold">{{ post.titulo }}</p>
            <p>{{ post.subtitulo }}</p>
        </div>
    </NuxtLink>
</template>

<script setup>
import { ROUTE_NAMES } from '~/constants/ROUTE_NAMES';

defineProps({
    post: {
        type: Object,
        required: true
    }
})
</script>