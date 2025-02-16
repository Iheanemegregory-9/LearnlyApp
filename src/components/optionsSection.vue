<template>
    <div class="grid gap-6">
        <div class="border flex justify-between items-center gap-3 shadow-2xs py-6 px-4 rounded-md cursor-pointer hover:shadow-sm hover:transition-all">
            <div class="flex space-x-4 items-end">
                <h2 class="text-lg font-extrabold">A</h2>
                <p class="text-md font-light truncate">Some random</p>
            </div>

            
        </div>

        <div class="border flex justify-between items-center gap-3 shadow-2xs py-6 px-4 rounded-md cursor-pointer hover:shadow-sm hover:transition-all" :class="{
            'border-green-500 bg-green-100': isCorrect === true,
                'border-red-500 bg-red-100': isCorrect === false,
                'border-gray-300': isCorrect === null
        }" @click="changeToCorrect">
            <div class="flex space-x-4 items-end">
                <h2 class="text-lg font-extrabold">A</h2>
                <p class="text-md font-light truncate">Some random</p>
            </div>

            <span v-if="isCorrect === true" class="text-green-500 text-xl items-end">
                <Icon icon="la:check-circle" width="34" height="34"   />
            </span>
            <span v-if="isCorrect === false" class="text-red-500 text-xl ">
                <Icon icon="weui:error-outlined" width="34" height="34"  />
            </span>
        </div>

        <div class="border flex justify-between items-center gap-3 shadow-2xs py-6 px-4 rounded-md cursor-pointer hover:shadow-sm hover:transition-all" :class="{
                'border-red-500 bg-red-100': isWrong === true,
                'border-gray-300': isCorrect === null
        }" @click="changeToWrong">
            <div class="flex space-x-4 items-end">
                <h2 class="text-lg font-extrabold">A</h2>
                <p class="text-md font-light truncate">Some random</p>
            </div>
            <span v-if="isWrong === true" class="text-red-500 text-xl">
                <Icon icon="weui:error-outlined" width="34" height="34"  />
            </span>
           
        </div>
    </div>

    <div v-if="isCorrect && !isWrong" class="py-6 bg-green-100 mt-4 rounded-md shadow px-2">
        <div class="flex items-center justify-start gap-2 pb-2">
            <span v-if="isCorrect === true" class="text-green-500 text-xl">
                <Icon icon="ei:check" width="34" height="34"   />
            </span>
            <p class="font-semibold text-md">
                Right!
            </p>
        </div>

        <p class="font-light text-md pl-10">
            You got the answer correct !
        </p>
    </div>

    <div v-if="isWrong" class="py-6 bg-red-100 mt-4 rounded-md shadow px-2">
        <div class="flex items-center justify-start gap-2 pb-2">
            <span v-if="isCorrect === true" class="text-red-500 text-xl">
                <Icon icon="weui:error-outlined" width="34" height="34"   />
            </span>
            <p class="font-semibold text-md">
                Wrong!
            </p>
        </div>

        <p class="font-light text-md pl-10">
            You got the answer wrong !
        </p>
    </div>
</template>

<script setup>

import { ref } from "vue";

    import { Icon } from "@iconify/vue";

    let isCorrect = ref(null)
    let isWrong = ref(null)

    const changeToCorrect = () => {
        isCorrect.value = true
    }


    const changeToWrong = () => {
        isWrong.value = true
        isCorrect.value = true
    }



</script>

<style lang="scss" scoped>

</style>