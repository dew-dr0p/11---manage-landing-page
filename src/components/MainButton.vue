<template>
    <button class="p-5 px-10 rounded-full font-bold text-secondary-LightGray bg-primary-BrightRed shadow-lg shadow-primary-BrightRed">{{ props.text }}</button>
</template>

<script setup lang="ts">
const props = defineProps<{
    text: string
}>()
</script>