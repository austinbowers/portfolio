<template>
    <img loading="lazy" class="bg-slate-800 pointer-events-none border border-slate-600 bg-opacity-50 rounded-md overflow-hidden h-full w-full aspect-square inline-flex items-center justify-center object-contain object-center"
    :src="props.url"/>
</template>

<script setup>
const props = defineProps({
    url: {
        type: String,
        default: ''
    }
})

</script>

<style scoped>

</style>