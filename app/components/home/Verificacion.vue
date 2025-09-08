<template>
    <DefaultSection class="md:flex-row md:!gap-0">
        <div class="md:w-1/2 flex flex-col gap-6 md:gap-8 py-16 lg:py-20 xxl:py-24 px-5 md:px-12 lg:px-16 xxl:px-20">
            <div class="flex items-center gap-1.5 fade-up">
                <Icon name="material-symbols:verified-user-outline" class="w-6 h-6 flex-shrink-0" />
                <p>Verificación</p>
            </div>
            <div class="flex flex-col gap-5 lg:gap-8 fade-up">
                <HeadingH2>
                    Identificá fácilmente
                    perfiles certificados con nuestros códigos QR
                </HeadingH2>
                <p class="lg:text-[1.125rem]">
                    Escaneando el código accedé a la información esencial de la certificación. Mantenete al día con las
                    últimas regulaciones y novedades en construcción en seco.
                </p>
            </div>
            <DefaultButton @click="scrollToIdentificar"
                class="flex items-center gap-2.5 hover:bg-dark border border-dark hover:text-white cursor-pointer">
                Aprender
                <Icon name="material-symbols:keyboard-arrow-down" class="w-6 h-6 flex-shrink-0" />
            </DefaultButton>
        </div>
        <div class="w-full flex md:w-1/2">
            <NuxtImg src="/images/home/Identifica-facilmente-con-QR.jpg" alt="Identificá fácilmente con QR"
                class="w-full h-[20.75rem] md:h-[36rem] lg:h-[38.25rem] xxl:h-[37.5rem] object-cover" />
        </div>
    </DefaultSection>
</template>

<script setup>
useFadeUp()

const scrollToIdentificar = () => {
    const identificarSection = document.getElementById('identificar')
    if (identificarSection) {
        const headerHeight = window.innerWidth >= 1080 ? 140 : 76
        
        const rect = identificarSection.getBoundingClientRect()
        const scrollTop = window.pageYOffset || document.documentElement.scrollTop
        const elementTop = rect.top + scrollTop
        
        window.scrollTo({
            top: elementTop - headerHeight,
            behavior: 'smooth'
        })
    }
}
</script>