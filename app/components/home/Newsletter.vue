<template>
    <DefaultSection class="py-16 md:px-16">
        <div class="w-full max-w-[1280px] flex flex-col items-center gap-6 md:gap-12 xxl:gap-16 mx-auto">
            <div class="flex flex-col items-center gap-6 md:gap-8 fade-up">
                <div class="flex items-center gap-1.5">
                    <Icon name="material-symbols:newsmode-outline-rounded" class="w-6 h-6 flex-shrink-0" />
                    <p>Artículos</p>
                </div>
                <HeadingH2 class="text-center">
                    Notas de interés
                    de nuestro newsletter
                </HeadingH2>
            </div>
            <CarouselStatic :slides-per-view="{ base: 1.3, sm: 2.2, md: 3, lg: 3, xl: 4, xxl: 4 }"
                :gap="{ base: 12, sm: 12, md: 16, lg: 16, xl: 16, xxl: 16 }" class="fade-up">
                <NewsletterCard v-for="(post, index) in posts" :key="index" :post="post" />
            </CarouselStatic>
        </div>
    </DefaultSection>
</template>

<script setup>
const posts = [
    {
        img: '/images/Placeholder.png',
        categoria: 'Actualizaciones',
        titulo: 'Entendiendo la resolución 236/2024',
        subtitulo: 'Explora los puntos clave del nuevo reglamento',
    },
    {
        img: '/images/Placeholder.png',
        categoria: 'Actualizaciones',
        titulo: 'Entendiendo la resolución 236/2024',
        subtitulo: 'Explora los puntos clave del nuevo reglamento',
    },
    {
        img: '/images/Placeholder.png',
        categoria: 'Actualizaciones',
        titulo: 'Entendiendo la resolución 236/2024',
        subtitulo: 'Explora los puntos clave del nuevo reglamento',
    },
    {
        img: '/images/Placeholder.png',
        categoria: 'Actualizaciones',
        titulo: 'Entendiendo la resolución 236/2024',
        subtitulo: 'Explora los puntos clave del nuevo reglamento',
    },
    {
        img: '/images/Placeholder.png',
        categoria: 'Actualizaciones',
        titulo: 'Entendiendo la resolución 236/2024',
        subtitulo: 'Explora los puntos clave del nuevo reglamento',
    },
];
</script>