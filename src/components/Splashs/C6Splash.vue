<template>
  <div
    class="
      absolute w-full h-screen flex justify-center
      bg-black top-0 bottom-0 right-0 left-0 lg:max-w-screen-sm mx-auto
      animate__animated animate__fadeInUp animate__faster
    "
  >

    <div class="flex justify-center mt-12 z-20"
      :class="{
        'loader--fx': state.translateLogoUp,
        'items-center': !state.logoItemsStart,
        'items-start': state.logoItemsStart
      }"
    >
      <div class="w-1/2">
        <img src="../../assets/images/c6bank.png" alt="Logotipo C6 Bank">
      </div>
    </div>

    <div
      v-if="state.backgroundImage"
      class="background-image z-10 animate__animated animate__fadeIn animate__faster"
    >
    </div>

    <div
      v-if="state.buttonsContainer"
      class="absolute z-20 bg-black opacity-25 top-0 w-full h-screen animate__animated animate_fadeIn animate__faster"
    >
    </div>

    <div
      v-if="state.buttonsContainer"
      class="absolute bottom-0 z-30 h-2/5 rounded-t-3xl w-full bg-white
        animate__animated animate__fadeInUp animate__faster"
    >
      <div class="w-full flex justify-center items-center pt-6 pb-4">
        <div class="bg-gray-200 p-4 rounded-full font-bold">
          AJ
        </div>
      </div>

      <div class="w-full flex justify-center items-center">
        <div class="text-3xl">
          Olá, Ademir
        </div>
      </div>

      <div class="w-full flex justify-between px-14 items-center mt-1">
        <div>
          Agência <strong>0001</strong>
        </div>
        <div>
          Conta Corrente <strong>123456-7</strong>
        </div>
      </div>

      <div class="w-full flex flex-col justify-center items-center mt-4">
        <button class="border-2 border-gray-500 text-gray-800 px-4 py-3 w-11/12 mb-2 rounded-full">
          ENTRAR COM OUTRA CONTA
        </button>

        <button
          class="px-4 py-3 w-11/12 mb-2 rounded-full
          bg-gradient-to-r from-yellow-300 to-yellow-400"
        >
          ENTRAR
        </button>
      </div>

    </div>

    <splashFinished v-if="state.splashFinished"/>
  </div>
</template>

<script>
import { onMounted, reactive } from 'vue'
import { wait } from '../../utils/timeout'
import SplashFinished from '../../components/SplashFinished'

export default {
  components: { SplashFinished },

  setup () {
    const state = reactive({
      translateLogoUp: false,
      logoItemsStart: false,
      backgroundImage: false,
      buttonsContainer: false,
      splashFinished: false
    })

    onMounted(() => {
      handleLogo()
    })

    async function handleLogo () {
      await wait(3000)
      state.translateLogoUp = true

      await wait(280)
      state.logoItemsStart = true

      handleBgImage()
    }

    async function handleBgImage () {
      await wait(300)
      state.backgroundImage = true

      handleButtonsContainer()
    }

    async function handleButtonsContainer () {
      await wait(600)
      state.buttonsContainer = true

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
@keyframes translate {
  0% {
    transform: translateY(0%);
  }
  100% {
    transform: translateY(-46%);
  }
}

.loader--fx {
  animation-name: translate;
  animation-duration: 300ms;
  animation-timing-function: ease-in-out;
}

.background-image {
  background: url('../../assets/images/c6bank-tech-person-1.jpg') no-repeat center center;
  width: 100%;
  height: 100%;
  position: absolute;
}
</style>
