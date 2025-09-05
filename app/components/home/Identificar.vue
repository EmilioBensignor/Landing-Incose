<template>
    <DefaultSection class="bg-dark text-white py-16 lg:py-20 px-5 md:px-12 lg:px-16">
        <div class="w-full max-w-[1280px] flex flex-col items-center gap-6 md:gap-12 xxl:gap-16 mx-auto">
            <div class="w-full flex flex-col gap-5 lg:gap-8">
                <HeadingH2 class="md:flex md:flex-col text-primary">
                    ¿Cómo identificar
                    <span>un perfil certificado?</span>
                </HeadingH2>
                <p class="md:max-w-[37.5rem] lg:text-xl">
                    Un perfil de acero certificado debe incluir un grabado en su ala con información detallada de su
                    fabricación.
                </p>
            </div>
            <div class="w-full grid lg:flex md:grid-cols-2 gap-6 md:gap-12 lg:gap-16 xxl:gap-20">
                <ul class="flex flex-col justify-between gap-6 md:gap-8">
                    <li v-for="(caracteristica, index) in caracteristicas.slice(0, Math.ceil(caracteristicas.length / 2))"
                        :key="index" class="flex gap-1.5 lg:text-[1.125rem]">
                        <Icon name="material-symbols:check-circle-outline" class="w-6 h-6 flex-shrink-0 text-primary" />
                        {{ caracteristica }}
                    </li>
                </ul>
                <ul class="flex flex-col justify-between gap-6 md:gap-8">
                    <li v-for="(caracteristica, index) in caracteristicas.slice(Math.ceil(caracteristicas.length / 2))"
                        :key="`second-${index}`" class="flex gap-1.5 lg:text-[1.125rem]">
                        <Icon name="material-symbols:check-circle-outline" class="w-6 h-6 flex-shrink-0 text-primary" />
                        {{ caracteristica }}
                    </li>
                </ul>
            </div>
        </div>
    </DefaultSection>
</template>

<script setup>
const caracteristicas = [
    'Nombre del fabricante',
    'Espesor de la chapa',
    'Tipo de recubrimiento galvanizado',
    'Grado estructural del acero (ZAR)',
    'Fecha y horario de elaboración',
    'Certificación IRAM-IAS U 500-243 (para construcción en seco)',
    'Certificación IRAM-IAS U 500-205 (para Steel Framing)',
    'Número de certificación del laboratorio',
]
</script>