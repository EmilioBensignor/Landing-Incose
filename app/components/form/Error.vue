<template>
    <div class="w-full min-h-1 flex items-center gap-1">
        <Icon name="material-symbols:error-outline" class="text-error" />
        <p class="text-error text-xs">
            <slot />
        </p>
    </div>
</template>