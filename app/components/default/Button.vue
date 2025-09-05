<template>
    <NuxtLink v-if="to" :to="to" class="w-max font-semibold transition-colors duration-300 py-3 px-6">
        <slot />
    </NuxtLink>
    <button v-else type="button" class="w-max font-semibold transition-colors duration-300 py-3 px-6">
        <slot />
    </button>
</template>

<script setup>
defineProps({
    to: {
        type: [String, Object],
        default: null
    }
})
</script>