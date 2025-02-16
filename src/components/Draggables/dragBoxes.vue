<template>
    <div class="shadow-sm rounded-xl mt-10 pt-10 px-10">
        
        <h2 class="text-sm font-semibold text-center">Drag the correct algebraic term below to match its definition
            above</h2>

        <div class="grid grid-cols-3 justify-center items-center gap-4 py-4" >
            <div class="w-35 h-15 py-10 px-10 flex items-center justify-center border border-dashed text-white border-white bg-gray-800 shadow-md rounded-md" v-for="item in getList(1)" :key="item.id" draggable="true" @dragstart="(startDrag($event, item))">
                {{ item.question }}
            </div>
        </div>
        <div class="grid grid-cols-2 justify-self-center items-center gap-4 mt-4" >
            <div class="w-35 h-15 py-10 px-10 flex items-center justify-center border border-dashed text-white border-white bg-gray-800 shadow-md rounded-md" v-for="item in getList(2)" :key="item.id" draggable="true" @dragstart="(startDrag($event, item.id))">
                {{ item.question }}
            </div>
        </div>

        <DragFooter />

    </div>
</template>

<script setup>

    import DragFooter from "./dragFooter.vue";

    defineProps({
        draggableQuestion: Array,
        getList: Function,
        startDrag: Function
    })
    


    

    

</script>

<style lang="scss" scoped></style>