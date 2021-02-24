<template>
  <component :is="state.name"/>
</template>

<script>
import { onMounted, reactive } from 'vue'
import { useRouter } from 'vue-router'
import C6Splash from '../../components/Splashs/C6Splash'
import ClaroSplash from '../../components/Splashs/ClaroSplash'

export default {
  components: { C6Splash, ClaroSplash },

  setup () {
    const router = useRouter()
    const state = reactive({
      name: ''
    })

    onMounted(() => {
      state.name = router.currentRoute.value.params.component
    })

    return {
      state,
      router
    }
  }
}
</script>
