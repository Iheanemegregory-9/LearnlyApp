<template>
    <div class="py-6 flex items-start justify-start">
        <div class="rounded-full cursor-pointer bg-purple-300 text-purple-900 py-2 px-2">
        <RouterLink to="/draggable">
            <Icon icon="solar:arrow-left-linear" width="34" height="34"   />
        </RouterLink>
        </div>
    </div>
</template>

<script setup>
    import { Icon } from "@iconify/vue";
    import { RouterLink } from "vue-router";
</script>

<style lang="scss" scoped>

</style>