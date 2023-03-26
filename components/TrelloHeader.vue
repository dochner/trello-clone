import DropdownMenu from './DropdownMenu.vue';

<template>
  <header class="w-full flex space-x-3 bg-lightBlue-600 text-white py-1.5 px-1">
    <RouterLink to="/" class="flex space-x-2 items-center">
      <div class="h-5 w-5 i-mdi-trello" />
      <h1 class="fw-bold text-xl">
        Trello
      </h1>
    </RouterLink>

    <div>
      <DropdownMenu label="Áreas de trabalho">
        <div class="flex flex-col p-4 space-y-4">
          <div class="text-xs fw-semibold text-gray-500 text-left">
            Suas Áreas de trabalho
          </div>
          <div class="flex items-center justify-start space-x-3 p-1 hover:bg-black/12">
            <div class="bg-gradient-to-b from-orange to-amber h-10 w-10 rounded fw-bold flex text-xl justify-center items-center">
              <span>Á</span>
            </div>
            <div>
              <h3 class="text-gray-700 fw-medium text-sm">
                Área de trabalho de ...
              </h3>
            </div>
          </div>

          <div class="flex items-center justify-start space-x-3 p-1 hover:bg-black/12">
            <div class="bg-gradient-to-b from-green to-lightblue h-10 w-10 rounded fw-bold flex text-xl justify-center items-center">
              <span>V</span>
            </div>
            <div>
              <h3 class="text-gray-700 fw-medium text-sm">
                Vuejs Roadmap
              </h3>
            </div>
          </div>
        </div>
      </DropdownMenu>
    </div>
  </header>
</template>
