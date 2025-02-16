<script setup>
  import GoalsSection from '@/components/goalsSection.vue'
  import QuestionsSection from '@/components/questionsSection.vue'
  import HeaderSection from '@/components/headerSection.vue'
  import OptionsSection from '@/components/optionsSection.vue'
  import DragAndDropSection from '@/components/Draggables/dropSection.vue';
</script>

<template>
  <div class="min-w-[520px] mx-auto py-6 ">
    <HeaderSection />
    <GoalsSection />
    <QuestionsSection :questionNumber=1 :question="'What is your name'" />
    <OptionsSection />
    <!-- <DragAndDropSection /> -->
  </div>
</template>
