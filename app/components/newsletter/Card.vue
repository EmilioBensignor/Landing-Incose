<template>
    <NuxtLink to="#" class="flex flex-col border border-dark">
        <NuxtImg :src="post.img" :alt="post.titulo" class="w-full h-44 object-cover" />
        <div class="flex flex-col gap-2 p-3">
            <p class="text-sm font-semibold">{{ post.categoria }}</p>
            <p class="text-xl font-bold">{{ post.titulo }}</p>
            <p>{{ post.subtitulo }}</p>
        </div>
    </NuxtLink>
</template>

<script setup>
defineProps({
    post: {
        type: Object,
        required: true
    }
})
</script>