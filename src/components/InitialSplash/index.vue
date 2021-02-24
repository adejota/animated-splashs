<template>
  <div
    class="
      absolute z-50 w-full h-screen flex justify-center items-start
      animate__animated animate__fadeIn animate__faster
      loader--fx
    ">
    <div class="flex justify-center items-end mt-8">
      <h1 class="text-4xl">Animated Splashs</h1>
      <icon
        name="splash"
        size="50"
        class="animate__animated animate__jackInTheBox animate__faster"
      />
    </div>
  </div>
</template>

<script>
import Icon from '../../components/Icon'

export default {
  components: { Icon }
}
</script>

<style lang="postcss" scoped>
@keyframes translate {
  0% {
    transform: translateY(40%);
  }
}
.loader--fx {
  animation-name: translate;
  animation-duration: 400ms;
  animation-timing-function: ease-in-out;
  animation-delay: 800ms;
}
</style>
