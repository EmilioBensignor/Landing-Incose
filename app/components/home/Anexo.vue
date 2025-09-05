<template>
    <DefaultSection class="bg-primary">
        <div class="flex flex-col gap-6 py-16 px-5">
            <div class="flex flex-col gap-5">
                <HeadingH2>Accedé al anexo de la resolución 236/2024</HeadingH2>
                <p>
                    Completá el siguiente formulario con tus datos personales para acceder al anexo oficial.
                </p>
            </div>
            <form @submit.prevent="handleSubmit" class="w-full flex flex-col gap-8">
                <div class="flex flex-col gap-4">
                    <div class="flex flex-col gap-2">
                        <label for="nombre" class="font-bold text-dark">
                            Nombre
                        </label>
                        <input type="text" id="nombre" v-model="form.nombre" placeholder="Ingrese su nombre"
                            class="w-full bg-white text-dark  placeholder:text-dark/60 outline-none p-3"
                            :class="errors.nombre ? 'border-error' : 'border-primary'" required>
                        <FormError v-if="errors.nombre">{{ errors.nombre }}</FormError>
                    </div>
                    <div class="flex flex-col gap-2">
                        <label for="apellido" class="font-bold text-dark">
                            Apellido
                        </label>
                        <input type="text" id="apellido" v-model="form.apellido" placeholder="Ingrese su apellido"
                            class="w-full bg-white text-dark  placeholder:text-dark/60 outline-none p-3"
                            :class="errors.apellido ? 'border-error' : 'border-primary'" required>
                        <FormError v-if="errors.apellido">{{ errors.apellido }}</FormError>
                    </div>

                    <div class="flex flex-col gap-2">
                        <label for="email" class="font-bold text-dark">
                            Correo electrónico
                        </label>
                        <input type="email" id="email" v-model="form.email" placeholder="Ingrese su correo electrónico"
                            class="w-full bg-white text-dark  placeholder:text-dark/60 outline-none p-3"
                            :class="errors.email ? 'border-error' : 'border-primary'" autocomplete="email" required>
                        <FormError v-if="errors.email">{{ errors.email }}</FormError>
                    </div>
                </div>
                <DefaultButton type="submit" class="bg-dark hover:bg-white text-white hover:text-dark">
                    Descargar anexo
                </DefaultButton>
            </form>
        </div>
        <NuxtImg src="/images/home/Anexo-resolucion-236-2024.jpg" alt="Anexo resolución 236/2024" class="w-full h-[22.5rem]" />
    </DefaultSection>
</template>

<script setup>
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

const handleSubmit = () => {
    if (!validateForm()) {
        return
    }

    console.log('Formulario enviado:', form.value)

    resetForm()
    clearErrors()
}
</script>