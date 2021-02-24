<template>
  <div class="bg-claro-color absolute w-full h-screen flex justify-center items-center bg-black top-0 bottom-0 right-0 left-0 lg:max-w-screen-sm mx-auto animate__animated animate__fadeInUp animate__faster">
    <div
      v-if="state.logoAnimation"
      class="w-1/2 animate__animated animate__flipInX"
    >
      <img src="../../assets/images/claro-logo-white.png" alt="Logotipo claro">
    </div>
  </div>

  <splashFinished v-if="state.splashFinished"/>
</template>

<script>
import { onMounted, reactive } from 'vue'
import { wait } from '../../utils/timeout'
import SplashFinished from '../../components/SplashFinished'

export default {
  components: { SplashFinished },

  setup () {
    const state = reactive({
      logoAnimation: false,
      splashFinished: false
    })

    onMounted(() => {
      triggerLogoAnimation()
    })

    async function triggerLogoAnimation () {
      await wait(1000)
      state.logoAnimation = true

      handleSplashFinished()
    }

    async function handleSplashFinished () {
      await wait(2000)
      state.splashFinished = true
    }

    return {
      state
    }
  }
}
</script>

<style lang="postcss" scoped>
.bg-claro-color {
  background-color: #EE2323;
}
</style>
