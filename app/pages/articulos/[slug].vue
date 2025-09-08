<template>
    <DefaultMain class="pt-[3.25rem] pb-16 px-5 md:px-12">
        <DefaultSection v-if="post" class="lg:max-w-screen-md xxl:max-w-screen-lg flex flex-col !gap-5 lg:mx-auto">
            <div class="w-full flex flex-col gap-3">
                <div class="flex items-center gap-1.5">
                    <Icon name="material-symbols:newsmode-outline-rounded" class="w-6 h-6 flex-shrink-0" />
                    <p>Artículos</p>
                </div>
                <HeadingH1>{{ post.titulo }}</HeadingH1>
                <p class="xxl:text-xl">{{ post.subtitulo }}</p>
                <div class="w-max bg-primary text-sm xxl:text-base font-semibold py-0.5 xxl:py-1 px-1.5 xxl:px-2">
                    <p>{{ post.categoria }}</p>
                </div>
            </div>
            <NuxtImg :src="post.img" :alt="post.titulo" class="w-full h-[11.5rem] sm:h-64 md:h-[22.5rem] xxl:h-[26.25rem] object-cover" />
            <div class="flex flex-col gap-4">
                <p v-for="(texto, index) in post.textos" :key="index" class="text-sm md:text-base">
                    {{ texto }}
                </p>
            </div>
        </DefaultSection>
        <DefaultSection v-else-if="!loading" class="not-found">
            <h1>Artículo no encontrado</h1>
            <p>El artículo que buscas no existe.</p>
            <NuxtLink to="/articulos" class="back-link">Volver a artículos</NuxtLink>
        </DefaultSection>
        <DefaultSection v-else>
            <p>Cargando artículo...</p>
        </DefaultSection>
    </DefaultMain>
</template>

<script setup>
import posts from '~/shared/posts.js'

const route = useRoute()
const loading = ref(true)

const post = computed(() => {
    return posts.find(p => p.slug === route.params.slug)
})

onMounted(() => {
    loading.value = false
})

if (!post.value) {
    throw createError({
        statusCode: 404,
        statusMessage: 'Artículo no encontrado'
    })
}

useSeoMeta({
    title: post.value?.titulo,
    ogTitle: post.value?.titulo,
    description: post.value?.subtitulo,
    ogDescription: post.value?.subtitulo,
    ogImage: post.value?.img
})
</script>
