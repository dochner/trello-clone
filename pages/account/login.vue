<script setup lang="ts">
definePageMeta({
  layout: 'auth',
})

const email = ref<string>('')
const emailIsValid = computed<boolean>(() => !!email.value?.length)

const handleLogin = () => {}
</script>

<template>
  <div
    class="bg-#f9fafc w-full min-h-screen flex items-center justify-center px-10 py-4"
  >
    <form
      class="rounded md:shadow border-px border-transparent md:border-dark/4 flex flex-col justify-center space-y-4 max-w-xs w-full p-4 md:bg-white"
      @submit.prevent="handleLogin"
    >
      <h1 class="text-center text-gray-600 fw-bold">
        Fazer login no Trello Clone
      </h1>

      <div class="w-full">
        <input
          type="text"
          name="email"
          placeholder="Insira o e-mail"
          class="rounded border-2 border-stone-300 bg-stone-50 h-10 focus:border-blue-300 w-full text-sm text-gray-600"
          :value="email"
          @input="(e) => (email = (e.target as HTMLInputElement).value) "
        >
      </div>
      <div>
        <button
          class="rounded fw-bold text-center w-full px-4 py-2.5 text-sm shadow active:shadow-none transition disabled:shadow-none"
          :un-bg="emailIsValid ? 'green-600' : 'indigo-50'"
          :un-text="emailIsValid ? 'white' : 'gray-400'"
          :disabled="!emailIsValid"
        >
          Continuar
        </button>
      </div>
      <p class="text-center fw-thin text-sm">
        OU
      </p>

      <button
        class="rounded bg-white-400 text-gray-600 fw-bold flex items-center text-sm justify-center space-x-3 border text-sm px-4 py-2.5 text-center w-full shadow active:shadow-none transition"
        disabled
      >
        <div class="h-5 w-5 i-logos:google-icon" />
        <span>Continuar com o Google</span>
      </button>

      <hr>

      <div class="w-full text-center">
        <RouterLink
          to="/account/signup"
          class="text-blue-800 fw-thin text-sm underline text-center"
        >
          Criar uma conta
        </RouterLink>
      </div>
    </form>
  </div>
</template>
