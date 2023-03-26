<script setup lang="ts">
import type { Column, Task } from '~~/types'
import { nanoid } from 'nanoid'
import Draggable from 'vuedraggable'

const columns = ref<Column[]>([
  {
    id: nanoid(),
    title: 'Backlog',
    tasks: [
      {
        id: nanoid(),
        title: 'Task 1',
       createdAt: new Date(),
      },
      {
        id: nanoid(),
        title: 'Task 2',
       createdAt: new Date(),
      },
      {
        id: nanoid(),
        title: 'Task 3',
       createdAt: new Date(),
      }
    ]
  },
  {
    id: nanoid(),
    title: 'Selected for Dev',
    tasks: []
  },
  {
    id: nanoid(),
    title: 'In Progress',
    tasks: []
  },
  {
    id: nanoid(),
    title: 'QA',
    tasks: []
  },
  {
    id: nanoid(),
    title: 'Done',
    tasks: []
  }
])

const alt = useKeyModifier("Alt")
</script>

<template>
  <div class="board flex gap-4 overflow-x-auto items-start ">
    <Draggable v-model="columns" group="columns" item-key="id" class="flex gap-4 overfow-x-auto items-start" :animation="150" handle=".drag-handle">
      <template #item="{element: column}: {element: Column}">
        <div class="column bg-gray-200 p-5 min-w-[250px]">
          <header>
            <DragHandle />
            {{ column?.title }}
          </header>

          <Draggable
            v-model="column.tasks"
            :group="{ name: 'tasks', pull: alt ? 'clone'  : true }"
            :animation="150"
            handle=".drag-handle"
            item-key="id"
            class="flex flex-col gap-4"
          >
            <template #item="{ element: task }: { element: Task }">
              <div>
                <TrelloBoardTask :task="task" />
              </div>
            </template>
          </Draggable>

          <footer>
            <button class="text-gray-500 ">+ Add a Card</button>
          </footer>
        </div>
      </template>
    </Draggable>
  </div>
</template>