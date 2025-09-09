<template>
    <DefaultSection class="sticky top-0 z-[1] text-white -mt-[4.75rem] lg:-mt-[8.75rem]">
        <picture class="w-full h-dvh">
            <source media="(min-width: 1440px)" srcset="/images/home/hero/Incose-Certificacion-Perfiles-Desktop-XL.webp">
            <source media="(min-width: 1080px)" srcset="/images/home/hero/Incose-Certificacion-Perfiles-Desktop.webp">
            <source media="(min-width: 768px)" srcset="/images/home/hero/Incose-Certificacion-Perfiles-Tablet.webp">
            <img src="/images/home/hero/Incose-Certificacion-Perfiles-Mobile.webp" alt="Incose Certificacion Perfiles"
                class="w-full h-dvh object-cover">
        </picture>
        <div
            class="w-full h-dvh flex flex-col justify-center md:items-center gap-6 md:gap-8 absolute top-0 left-0 px-5">
            <HeadingH1 class="md:max-w-[33rem] lg:max-w-[38rem] xxl:max-w-[42rem] md:text-center"><span
                    class="text-primary">La certificación</span> de
                perfiles ya es una
                exigencia.</HeadingH1>
            <p
                class="md:max-w-[28rem] lg:max-w-[52rem] md:text-center lg:text-xl lg:!leading-8 font-bold md:!leading-6">
                Perfiles certificados para Construcción en Seco y Steel Framing.
                Conocé más sobre la nueva <span class="text-primary">Resolución 236/2024</span>. No arriesgues la
                seguridad ni el futuro de tu obra.
            </p>
            <DefaultButton @click="scrollToAnexo"
                class="bg-primary hover:bg-dark text-dark hover:text-primary cursor-pointer">Descargá los puntos clave
            </DefaultButton>
        </div>
    </DefaultSection>
</template>

<script setup>
const scrollToAnexo = () => {
    const anexoSection = document.getElementById('anexo')
    if (anexoSection) {
        const headerHeight = window.innerWidth >= 1080 ? 140 : 76

        const rect = anexoSection.getBoundingClientRect()
        const scrollTop = window.pageYOffset || document.documentElement.scrollTop
        const elementTop = rect.top + scrollTop

        window.scrollTo({
            top: elementTop - headerHeight,
            behavior: 'smooth'
        })
    }
}
</script>