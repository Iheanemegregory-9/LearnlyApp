<script setup>

    defineProps({
        questionNumber: Number,
    question: String
})


</script>

<template>
    <div class="flex flex-col gap-3 py-4">
        <h2 class="font-extrabold">Question {{ questionNumber }}</h2>
        <p class="font-light">{{ question }}</p>
    </div>
</template>



<style scoped>

</style>