<template>
    <div class="flex justify-center items-center gap-8 py-8">
        <div class="rounded-md cursor-pointer bg-purple-100 shadow text-purple-900 py-2 px-2">
            <Icon icon="mage:reload" width="34" height="34" />
            <!-- <Icon icon="mage:reload" width="24" height="24" /> -->
        </div>
        <button class="py-5 px-10 bg-purple-700 rounded-xl shadow text-white flex items-center gap-4 cursor-pointer" @click="$router.push('/')">
            Continue 

            <span>
                <Icon icon="mynaui:arrow-right" width="34" height="34" />
            </span>
        </button>
    </div>
</template>

<script setup>

import { Icon } from "@iconify/vue";


</script>

<style lang="scss" scoped>

</style>