<template>
    <!-- header -->
    <div class="flex justify-between items-center gap-3">
        <div class="rounded-md cursor-pointer bg-purple-100 shadow text-purple-900 py-2 px-2">
            <RouterLink to="/">
                <Icon icon="solar:arrow-left-linear" width="34" height="34" />
            </RouterLink>
        </div>
        <h2 class="text-lg font-extrabold">Course Preview</h2>
        <div class="rounded-md cursor-pointer bg-purple-100 shadow text-purple-900 py-2 px-2">
            <Icon icon="lineicons:question-mark-circle" width="34" height="34" />
        </div>
    </div>

    <!-- instructions -->

    <div class="flex justify-center items-center py-14">
        <h2 class="text-lg font-extrabold">Match The Algebraic Terms</h2>
    </div>

    <!-- boxes -->

    <div class="grid grid-cols-2 justify-center items-center gap-4">
        <div 
            v-for="index in 4" 
            :key="index"
            class="w-55 h-25 py-10 px-10 border border-dashed border-purple-600 bg-purple-200 rounded-md" 
            @drop="onDrop($event, index)" 
            @dragover.prevent
            @dragenter.prevent
        >

        
    
    </div>
        <div 
            class="w-55 h-25 py-10 px-10 border border-dashed border-purple-600 bg-purple-200 rounded-md col-span-2 justify-self-center"
            @drop="onDrop($event, index)"
            @dragover.prevent
            @dragenter.prevent
        ></div>
    </div>

    <DragBoxes :startDrag="setData" :draggable-question="draggableQuestion" :get-list="getList" :start-drag="startDrag"/>
</template>

<script setup>
    import { Icon } from "@iconify/vue";
    import DragBoxes from "./dragBoxes.vue";
    import { RouterLink } from "vue-router";

    import { ref } from "vue";




    const draggableQuestion = ref(
        [
            {
                "question": "Variable",
                "id": 0,
                "list": 1
            },
            {
                "question": "Contacts",
                "id": 1,
                "list": 1
            },
            {
                "question": "Some Texts",
                "id": 2,
                "list": 1
            },
            {
                "question": "Equation",
                "id": 3,
                "list": 2
            },
            {
                "question": "Equation",
                "id": 4,
                "list": 2
            }
        ]
    )


    const getList = (list) => {
        return draggableQuestion.value.filter((item) => item.list === list)
    }

    const setData = (event, item) => {
        event.dataTransfer.setData('itemId', item.id)
    }


    const startDrag = (event, item) => {
        console.log(item);
        event.dataTransfer.dropEffects = 'move'
        event.dataTransfer.effectAllowed = 'move'
    }


    const onDrop = (event, list) => {
        const itemID = event.dataTransfer.getData('itemID')
        const item = draggableQuestion.value.find((item) => item.id == itemID)
        item.list = list
    }

    
    
</script>

<style lang="scss" scoped></style>
