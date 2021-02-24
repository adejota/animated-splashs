<template>
  <initialSplash
    v-if="!state.finishedInitialSplash"
  />

  <div v-else>
    <div class="w-full flex justify-center items-start z-0">
      <div class="flex justify-center items-end mt-8">
        <h1 class="text-4xl">Animated Splashs</h1>
        <icon
          name="splash"
          size="50"
        />
      </div>
    </div>

    <div class="animate__animated animate__fadeIn animate__faster py-8 px-6 lg:max-w-screen-sm mx-auto">
      <p class="text-xl text-center">Biblioteca de telas de abertura para aplicativos web</p>

      <div class="mt-12 flex flex-col">
        <h2 class="text-2xl">Destaques</h2>

        <div
          class="mt-4 flex justify-start w-1/4">

          <div
            @click="router.push({ name: 'Splash', params: { component: 'C6Splash' } })"
            class="flex flex-col items-center cursor-pointer mr-4"
          >
            <icon
              name="c6Logo"
              size="76"
            />
            <span class="mt-2">C6 Bank</span>
          </div>

          <div
            @click="router.push({ name: 'Splash', params: { component: 'ClaroSplash' } })"
            class="flex flex-col items-center cursor-pointer"
          >
            <icon
              name="claroLogo"
              size="76"
            />
            <span class="mt-2">Claro</span>
          </div>

        </div>

      </div>

      <div class="mt-12">
        <h2 class="text-2xl">Todos os Splashs</h2>
      </div>

    </div>

  </div>
</template>

<script>
import { onMounted, reactive } from 'vue'
import { useRouter } from 'vue-router'
import { wait } from '../../utils/timeout'
import InitialSplash from '../../components/InitialSplash'
import Icon from '../../components/Icon'

export default {
  components: { Icon, InitialSplash },

  setup () {
    const router = useRouter()
    const state = reactive({
      finishedInitialSplash: false,
      openC6Splash: false
    })

    onMounted(() => {
      handleInitialSplash()
    })

    async function handleInitialSplash () {
      await wait(1300)
      state.finishedInitialSplash = true
    }

    return {
      state,
      router
    }
  }
}
</script>
