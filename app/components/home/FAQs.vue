<template>
    <DefaultSection class="py-16 px-5 md:px-12">
        <div class="w-full max-w-[1280px] flex flex-col items-center gap-6 md:gap-12 xxl:gap-16 mx-auto">
            <HeadingH2 class="md:w-full">Preguntas frecuentes</HeadingH2>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-4 lg:gap-y-6 lg:gap-x-16 xxl:gap-y-10 xxl:gap-x-20">
                <FaqAccordion v-for="(faq, index) in faqs" :key="index" :faq="faq" />
            </div>
        </div>
    </DefaultSection>
</template>

<script setup>
const faqs = [
    {
        pregunta: "¿Qué productos están alcanzados por esta nueva normativa?",
        respuesta: "Los perfiles de acero galvanizado para construcción en seco y Steel Framing están incluidos en el Reglamento Técnico de la Resolución 236/2024. (incluir botón con link al Anexo 2)",
    },
    {
        pregunta: "¿Cómo puedo verificar si un perfil está certificado?",
        respuesta: "Buscá el grabado en el ala del perfil que debe incluir el nombre del fabricante y el número del ente certificador IRAM o TÜV. Próximamente, los paquetes de perfiles también llevarán una etiqueta con un código QR que podrás escanear para acceder al certificado y la declaración jurada del fabricante.",
    },
    {
        pregunta: "¿Un informe de laboratorio de calidad es lo mismo que una certificación?",
        respuesta: "No. Un informe de laboratorio se realiza sobre una muestra puntual y no garantiza que toda la producción cumpla con la norma. La certificación, en cambio, implica un sistema de auditorías y trazabilidad que asegura la calidad de toda la producción.",
    },
    {
        pregunta: "¿Qué pasa si uso perfiles no certificados?",
        respuesta: "Además de ser una infracción a las reglamentaciones, compromete la seguridad estructural y la durabilidad de la obra. Expone al proyecto a riesgos de fallas y a los profesionales a sanciones legales por incumplimiento.",
    },
];
</script>