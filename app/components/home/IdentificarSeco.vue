<template>
    <DefaultSection id="identificarSeco" class="bg-dark text-white py-16 lg:py-20 px-5 md:px-12 lg:px-16">
        <div class="w-full max-w-[1280px] flex flex-col items-center gap-6 md:gap-12 xxl:gap-16 mx-auto">
            <div class="w-full flex flex-col gap-5 lg:gap-8 fade-up">
                <HeadingH2 class="md:flex md:flex-col text-white">
                    ¿Cómo identificar un perfil certificado
                    <span class="text-primary">para construcción en seco?</span>
                </HeadingH2>
                <p class="md:max-w-[38rem] lg:text-xl">
                    Un perfil de acero certificado para construcción en seco debe incluir un grabado en su ala con información detallada de su
                    fabricación.
                </p>
            </div>
            <div class="w-full grid lg:flex md:grid-cols-2 gap-6 md:gap-12 lg:gap-16 xxl:gap-40">
                <ul class="flex flex-col justify-between gap-6 md:gap-8">
                    <li v-for="(caracteristica, index) in caracteristicas.slice(0, Math.ceil(caracteristicas.length / 2))"
                        :key="index" class="flex gap-1.5 lg:text-[1.125rem] fade-up">
                        <Icon name="material-symbols:check-circle-outline" class="w-6 h-6 flex-shrink-0 text-primary" />
                        {{ caracteristica }}
                    </li>
                </ul>
                <ul class="flex flex-col justify-between gap-6 md:gap-8">
                    <li v-for="(caracteristica, index) in caracteristicas.slice(Math.ceil(caracteristicas.length / 2))"
                        :key="`second-${index}`" class="flex gap-1.5 lg:text-[1.125rem] fade-up">
                        <Icon name="material-symbols:check-circle-outline" class="w-6 h-6 flex-shrink-0 text-primary" />
                        {{ caracteristica }}
                    </li>
                </ul>
            </div>
        </div>
    </DefaultSection>
</template>

<script setup>
useFadeUp();

const caracteristicas = [
    'Nombre del fabricante',
    'Designación del perfil',
    'Espesor de chapa base en mm',
    'Código de trazabilidad',
    'Certificación IRAM-IAS U 500-243',
    'Número de certificación del laboratorio (Opcional)',
]
</script>