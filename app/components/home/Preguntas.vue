<template>
    <DefaultSection>
        <NuxtImg src="/images/home/Preguntas-Incose.jpg" alt="Preguntas Incose"
            class="w-full h-[20.75rem] md:h-[19rem] lg:h-[22.5rem] xxl:h-[24.5rem] object-cover" />
        <div
            class="h-[20.75rem] md:h-[19rem] lg:h-[22.5rem] xxl:h-[24.5rem] flex flex-col justify-center items-center gap-6 lg:gap-8 absolute top-0 text-white py-16 lg:py-20 xxl:py-24 px-5 md:px-12">
            <div class="flex flex-col items-center gap-5 lg:gap-8 fade-up">
                <HeadingH2 class="max-w-56 md:max-w-full text-center">¿Aún tenés preguntas?</HeadingH2>
                <p class="max-w-56 lg:max-w-full text-center lg:text-xl">Estamos aca para ayudarte con cualquier
                    consulta</p>
            </div>
            <DefaultButton @click="scrollToFooter" class="bg-primary hover:bg-dark text-dark hover:text-primary cursor-pointer fade-up">Contacto</DefaultButton>
        </div>
    </DefaultSection>
</template>

<script setup>
useFadeUp();

const scrollToFooter = () => {
    const footerSection = document.getElementById('footer')
    if (footerSection) {
        const headerHeight = window.innerWidth >= 1080 ? 140 : 76
        
        const rect = footerSection.getBoundingClientRect()
        const scrollTop = window.pageYOffset || document.documentElement.scrollTop
        const elementTop = rect.top + scrollTop
        
        window.scrollTo({
            top: elementTop - headerHeight,
            behavior: 'smooth'
        })
    }
}
</script>