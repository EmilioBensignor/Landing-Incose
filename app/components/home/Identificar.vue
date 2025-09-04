<template>
    <DefaultSection class="bg-dark text-white py-16 px-5">
        <div class="flex flex-col gap-5">
            <HeadingH2 class="text-primary">
                ¿Cómo identificar un
                perfil certificado?
            </HeadingH2>
            <p>
                Un perfil de acero certificado debe incluir un grabado en su ala con información detallada de su
                fabricación.
            </p>
        </div>
        <ul class="flex flex-col gap-3">
            <li v-for="(caracteristica, index) in caracteristicas" :key="index" class="flex gap-1.5">
                <Icon name="material-symbols:check-circle-outline" class="w-6 h-6 flex-shrink-0 text-primary" />
                {{ caracteristica }}
            </li>
        </ul>
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