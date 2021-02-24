<template>
  <div
    class="black-cover-color absolute z-40 top-0 h-screen w-full flex flex-col
      justify-center items-center animate__animated animate__fadeIn animate__faster"
  >
    <div class="bg-white z-50 w-3/4 h-1/4 rounded-2xl animate__animated animate__fadeInDownBig animate__faster">
      <div class="flex justify-center items-end pt-8 pb-6 mr-2">
        <h1 class="text-2xl">Splash finalizado</h1>
        <icon
          name="splash"
          size="32"
          class="ml-2"
        />
      </div>

      <div class="flex justify-center w-full px-4">
        <a href="https://www.google.com/" target="_blank"
          class="button-border-color w-4/5 flex justify-center items-center p-4 mx-2 rounded-full focus:outline-none"
        >
          <icon
            name="github"
            size="36"
            color="#00C8FF"
          />
        </a>

        <button
          @click="router.push({ name: 'Home' })"
          class="button-filled-bg-color w-4/5 flex justify-center items-center p-4 mx-2 rounded-full focus:outline-none"
        >
          <icon
            name="home"
            size="32"
            color="white"
          />
        </button>
      </div>
    </div>
  </div>

</template>

<script>
import Icon from '../Icon'
import { useRouter } from 'vue-router'

export default {
  components: { Icon },

  setup () {
    const router = useRouter()

    return {
      router
    }
  }

}
</script>

<style lang="postcss" scoped>
.black-cover-color {
  background-color: rgba(0, 0, 0, 0.26);
}

.button-filled-bg-color {
  background-color: #00C8FF;
}

.button-border-color {
  border: 2px solid #00C8FF;
}
</style>
