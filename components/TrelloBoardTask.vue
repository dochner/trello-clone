<script setup lang="ts">
import type { Task } from '~~/types'

defineProps<{
  task: Task
}>()
</script>

<template>
  <div :title="task?.title" class="task bg-white p-3 rounded shadow max-w-[250px]">
    <DragHandle />
    <span>
      {{ task?.title }}
    </span>
  </div>
</template>

<style>
.sortable-chosen .task {
  background-color: green;
}

.sortable-drag .task {
  transform: rotate(5deg);
}

.sortable-ghost .task::after {
  content: "";
  @apply absolute top-0 bottom-0 left-0 right-0 bg-slate-300;
}
</style>
