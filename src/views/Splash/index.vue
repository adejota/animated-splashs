<template>
  <component :is="state.name"/>
</template>

<script>
import { reactive } from 'vue'
import { useRouter } from 'vue-router'
import C6Splash from '../../components/Splashs/C6Splash'
import ClaroSplash from '../../components/Splashs/ClaroSplash'
import NetClaroSplash from '../../components/Splashs/NetClaroSplash'

export default {
  components: { C6Splash, ClaroSplash, NetClaroSplash },

  setup () {
    const router = useRouter()
    const state = reactive({
      name: router.currentRoute.value.params.component
    })

    return {
      state,
      router
    }
  }
}
</script>
