<script setup lang="ts">
import { onClickOutside } from '@vueuse/core'

defineProps<{
  label: string
}>()

const show = ref<boolean>(false)
const toggleShow = () => {
  show.value = !show.value
}

const dropdownEl = ref<HTMLElement>()

onClickOutside(dropdownEl, () => {
  show.value = false
})
</script>

<template>
  <button ref="dropdownEl" class="flex px-3 py-1 relative" :un-bg="show && 'black/12'" @click="toggleShow">
    <div>
      {{ label }}
    </div>
    <div class="i-mdi-chevron-down h-6 w-6" />

    <Transition
      enter-from-class=""
      enter-active-class=""
      enter-to-class=""
      appear-from-class=""
      appear-active-class=""
      appear-to-class=""
      leave-from-class=""
      leave-active-class=""
      leave-to-class=""
    >
      <div v-if="show" class="bg-white border border-gray-300 shadow-lg absolute top-[120%] left-0 w-max rounded">
        <slot />
      </div>
    </Transition>
  </button>
</template>
