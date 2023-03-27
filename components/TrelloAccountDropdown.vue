<script setup lang="ts">
</script>

<template>
  <div class="relative">
    <button class="p-1 hover:bg-lightblue-700 rounded-full">
      <div class="rounded-full overflow-hidden h-6 w-6">
        <img src="https://trello-members.s3.amazonaws.com/56d8cf6d7a296bb9c66d5cd6/597dc0ba5bf6374f83121366c1c21f41/50.png" alt="Trello member avatar image" width="40">
      </div>
    </button>

    <div class="absolute top-[120%] right-0 border border-gray-300 shadow-lg rounded bg-white py-2">
      <div class="flex flex-col">
        <h3 class="fw-bold text-stone-500 tracking-tight text-11px mt-4 mb-2 mx-5">
          CONTA
        </h3>

        <div class="flex space-x-2 py-2 px-5">
          <div class="rounded-full overflow-hidden h-10 w-10">
            <img src="https://trello-members.s3.amazonaws.com/56d8cf6d7a296bb9c66d5cd6/597dc0ba5bf6374f83121366c1c21f41/50.png" alt="Trello member avatar image" width="40">
          </div>

          <div>
            <h4 class="text-gray-700 text-sm">
              Douglas Ochner
            </h4>
            <p class="text-stone-300 text-xs">
              dochner@example.com
            </p>
          </div>
        </div>

        <RouterLink to="/account" class="text-gray-700 py-2 px-5 hover:bg-black/4">
          <div class="flex justify-between items-center">
            <span class="text-sm">Gerenciar conta</span>
            <UnoIcon class="h-4 w-4 i-mdi-arrow-right" />
          </div>
        </RouterLink>

        <hr class="my-3">

        <button class="text-gray-700 py-2 px-5 hover:bg-black/4">
          <div class="w-full flex justify-between items-center">
            <span class="text-sm">Fazer Logout</span>

            <UnoIcon class="h-4 w-4 i-mdi-logout" />
          </div>
        </button>
      </div>
    </div>
  </div>
</template>
