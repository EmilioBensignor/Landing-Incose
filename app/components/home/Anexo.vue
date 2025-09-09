<template>
    <DefaultSection id="anexo" class="md:flex-row-reverse md:!gap-0 bg-primary">
        <div class="md:w-1/2 flex flex-col gap-6 md:gap-12 py-16 lg:py-20 xxl:py-24 px-5 md:px-12 lg:px-16 xxl:px-20">
            <div class="flex flex-col gap-5 lg:gap-8 fade-up">
                <HeadingH2>Accedé al anexo de la resolución 236/2024</HeadingH2>
                <p class="lg:text-xl">
                    Completá el siguiente formulario con tus datos personales para acceder al anexo oficial.
                </p>
            </div>
            <form @submit.prevent="handleSubmit" class="w-full flex flex-col gap-8 fade-up">
                <div class="flex flex-col gap-4 lg:gap-6">
                    <div class="flex flex-col gap-2">
                        <label for="nombre" class="lg:text-xl font-bold text-dark">
                            Nombre
                        </label>
                        <input type="text" id="nombre" v-model="form.nombre" placeholder="Ingrese su nombre"
                            class="w-full bg-white lg:text-xl text-dark  placeholder:text-dark/60 outline-none p-3"
                            :class="errors.nombre ? 'border-error' : 'border-primary'" required>
                        <FormError v-if="errors.nombre">{{ errors.nombre }}</FormError>
                    </div>
                    <div class="flex flex-col gap-2">
                        <label for="apellido" class="lg:text-xl font-bold text-dark">
                            Apellido
                        </label>
                        <input type="text" id="apellido" v-model="form.apellido" placeholder="Ingrese su apellido"
                            class="w-full bg-white lg:text-xl text-dark  placeholder:text-dark/60 outline-none p-3"
                            :class="errors.apellido ? 'border-error' : 'border-primary'" required>
                        <FormError v-if="errors.apellido">{{ errors.apellido }}</FormError>
                    </div>

                    <div class="flex flex-col gap-2">
                        <label for="email" class="lg:text-xl font-bold text-dark">
                            Correo electrónico
                        </label>
                        <input type="email" id="email" v-model="form.email" placeholder="Ingrese su correo electrónico"
                            class="w-full bg-white lg:text-xl text-dark  placeholder:text-dark/60 outline-none p-3"
                            :class="errors.email ? 'border-error' : 'border-primary'" autocomplete="email" required>
                        <FormError v-if="errors.email">{{ errors.email }}</FormError>
                    </div>
                </div>
                <DefaultButton type="submit" class="bg-dark hover:bg-white text-white hover:text-dark"
                    :disabled="isSubmitting">
                    {{ isSubmitting ? 'Enviando...' : 'Descargar anexo' }}
                </DefaultButton>
            </form>
        </div>
        <div class="w-full md:w-1/2">
            <picture class="w-full">
                <source media="(min-width: 1440px)"
                    srcset="/images/home/anexo/Anexo-resolucion-236-2024-Desktop-XL.webp">
                <source media="(min-width: 1080px)" srcset="/images/home/anexo/Anexo-resolucion-236-2024-Desktop.webp">
                <source media="(min-width: 768px)" srcset="/images/home/anexo/Anexo-resolucion-236-2024-Tablet.webp">
                <img src="/images/home/anexo/Anexo-resolucion-236-2024-Mobile.webp" alt="Anexo resolución 236/2024"
                    class="w-full h-[22.5rem] sm:h-[34rem] md:h-[44.25rem] lg:h-[50rem] object-cover">
            </picture>
        </div>
    </DefaultSection>

    <Teleport to="body">
        <Transition name="modal" appear>
            <div v-if="showModal"
                class="flex items-center justify-center fixed inset-0 z-50 bg-black bg-opacity-40 p-4">
                <Transition name="modal-content" appear>
                    <div v-if="showModal"
                        class="w-full max-w-72 md:max-w-[34.5rem] lg:max-w-[40.75rem] xxl:max-w-[59.5rem] relative bg-white py-12 lg:py-16 xxl:py-20 px-6 md:px-16">
                        <button @click="closeModal" class="absolute top-3 lg:top-5 xxl:top-7 right-6 text-dark">
                            <Icon name="material-symbols:cancel-outline" class="w-6 h-6" />
                        </button>
                        <div class="flex flex-col items-center gap-3 md:gap-4 text-center">
                            <p
                                class="text-[1.75rem] md:text-[2rem] lg:text-[2.5rem] xxl:text-[3rem] text-dark font-bold">
                                Ya puedes acceder al anexo de la resolución 236/2024
                            </p>
                            <DefaultButton @click="downloadPDF"
                                class="flex items-center justify-center gap-2 bg-primary hover:bg-primary/90 text-dark">
                                Descargar Anexo
                                <Icon name="material-symbols:download-rounded" class="w-4 h-4 flex-shrink-0" />
                            </DefaultButton>
                        </div>
                    </div>
                </Transition>
            </div>
        </Transition>
    </Teleport>
</template>

<script setup>
useFadeUp();

const supabase = useSupabaseClient();
const isSubmitting = ref(false);
const showModal = ref(false);

const form = ref({
    nombre: '',
    apellido: '',
    email: ''
})

const errors = ref({
    nombre: '',
    apellido: '',
    email: ''
})

const validateForm = () => {
    clearErrors()
    let isValid = true

    if (form.value.nombre.length < 2) {
        errors.value.nombre = 'El nombre debe tener al menos 2 caracteres'
        isValid = false
    } else if (form.value.nombre.length > 30) {
        errors.value.nombre = 'El nombre no puede exceder los 30 caracteres'
        isValid = false
    }

    if (form.value.apellido.length < 2) {
        errors.value.apellido = 'El apellido debe tener al menos 2 caracteres'
        isValid = false
    } else if (form.value.apellido.length > 40) {
        errors.value.apellido = 'El apellido no puede exceder los 40 caracteres'
        isValid = false
    }

    const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/
    if (!emailRegex.test(form.value.email)) {
        errors.value.email = 'Por favor ingrese un correo electrónico válido'
        isValid = false
    }

    return isValid
}

const clearErrors = () => {
    errors.value = {
        nombre: '',
        apellido: '',
        email: ''
    }
}

const resetForm = () => {
    form.value = {
        nombre: '',
        apellido: '',
        email: ''
    }
}

const handleSubmit = async () => {
    if (!validateForm()) {
        return
    }

    isSubmitting.value = true;

    try {
        const { error } = await supabase
            .from('contactos')
            .insert({
                nombre: form.value.nombre,
                apellido: form.value.apellido,
                mail: form.value.email
            });

        if (error) {
            console.error('Error al enviar formulario:', error);
            return;
        }

        console.log('Formulario enviado exitosamente');
        showModal.value = true;
        resetForm();
        clearErrors();
    } catch (error) {
        console.error('Error inesperado:', error);
    } finally {
        isSubmitting.value = false;
    }
}

const closeModal = () => {
    showModal.value = false;
}

const downloadPDF = () => {
    const link = document.createElement('a');
    link.href = '/Anexo-Resolucion-236-2024.pdf';
    link.download = 'Anexo-Resolucion-236-2024.pdf';
    document.body.appendChild(link);
    link.click();
    document.body.removeChild(link);
}
</script>

<style scoped>
.modal-enter-active,
.modal-leave-active {
    transition: opacity 0.3s ease;
}

.modal-enter-from,
.modal-leave-to {
    opacity: 0;
}

.modal-content-enter-active,
.modal-content-leave-active {
    transition: transform 0.3s ease, opacity 0.3s ease;
}

.modal-content-enter-from,
.modal-content-leave-to {
    transform: scale(0.8) translateY(-20px);
    opacity: 0;
}
</style>