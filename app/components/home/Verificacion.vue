<template>
    <DefaultSection>
        <div class="flex flex-col gap-6 py-16 px-5">
            <div class="flex items-center gap-1.5">
                <Icon name="material-symbols:verified-user-outline" class="w-6 h-6 flex-shrink-0" />
                <p>Verificación</p>
            </div>
            <div class="flex flex-col gap-5">
                <HeadingH2>
                    Identificá fácilmente
                    perfiles certificados con nuestros códigos QR
                </HeadingH2>
                <p>
                    Escaneando el código accedé a la información esencial de la certificación. Mantenete al día con las
                    últimas regulaciones y novedades en construcción en seco.
                </p>
            </div>
            <DefaultButton to="#" class="flex items-center gap-2.5 border border-dark">
                Aprender
                <Icon name="material-symbols:keyboard-arrow-down" class="w-6 h-6 flex-shrink-0" />
            </DefaultButton>
        </div>
        <NuxtImg src="/images/home/Identifica-facilmente-con-QR.jpg" alt="Identificá fácilmente con QR"
            class="w-full h-[20.75rem]" />
    </DefaultSection>
</template>