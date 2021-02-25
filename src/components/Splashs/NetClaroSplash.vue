<template>
  <div class="bg-net-color absolute w-full h-screen flex justify-center items-center
    top-0 bottom-0 right-0 left-0 lg:max-w-screen-sm mx-auto
    animate__animated animate__fadeInUp animate__faster z-10"
  >
    <div
      v-if="state.netLogoAnimation"
      class="w-1/2 animate__animated animate__fadeIn flex justify-center items-center"
      :class="{
        'animate__zoomOut animate__faster': state.netLogoAnimationFinished
      }"
    >
      <icon
        name="netLogo"
        size="220"
      />
    </div>

    <div
      v-if="state.claroLogoAnimation"
      class="bg-claro-color absolute w-full h-screen flex justify-center items-center
        top-0 bottom-0 right-0 left-0 lg:max-w-screen-sm mx-auto
        animate__animated animate__fadeIn animate__faster z-30"
    >
      <icon
        name="oClaro"
        size="76"
        class="absolute animate__animated animate__zoomIn animate__faster"
        :class="{
          'translate-to-fit--fx': state.claroLogoAnimationFinished
        }"
      />

      <div
        v-if="state.completeLogoAnimation"
        class="animate__animated animate__fadeIn animate__faster"
      >
        <img src="../../assets/images/minhaclaroresidencial.png" alt="">
      </div>
    </div>
  </div>

  <splashFinished v-if="state.splashFinished"/>
</template>

<script>
import { onMounted, reactive } from 'vue'
import { wait } from '../../utils/timeout'
import SplashFinished from '../../components/SplashFinished'
import Icon from '../../components/Icon'

export default {
  components: { SplashFinished, Icon },

  setup () {
    const state = reactive({
      netLogoAnimation: false,
      netLogoAnimationFinished: false,
      claroLogoAnimation: false,
      claroLogoAnimationFinished: false,
      completeLogoAnimation: false,
      splashFinished: false
    })

    onMounted(() => {
      triggerNetLogoAnimation()
    })

    async function triggerNetLogoAnimation () {
      await wait(1000)
      state.netLogoAnimation = true

      handleNetLogoAnimation()
    }

    async function handleNetLogoAnimation () {
      await wait(3200)
      state.netLogoAnimationFinished = true

      triggerClaroLogoAnimation()
    }

    async function triggerClaroLogoAnimation () {
      state.claroLogoAnimation = true

      handleClaroLogoAnimation()
    }

    async function handleClaroLogoAnimation () {
      await wait(1000)
      state.claroLogoAnimationFinished = true

      triggerCompleteLogo()
    }

    async function triggerCompleteLogo () {
      await wait(300)
      state.completeLogoAnimation = true

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

.bg-net-color {
  background-image: linear-gradient(#0052D9, #001FB5);
}

@keyframes translate {
  0% {
    transform: translate(0, 0);
  }
  100% {
    transform: translate(65px, -9px);
  }
}

.translate-to-fit--fx {
  animation-name: translate;
  animation-duration: 300ms;
  animation-timing-function: ease-in-out;
}
</style>
