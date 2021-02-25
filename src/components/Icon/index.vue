<template>
  <component :is="name" v-bind="$props" />
</template>

<script>
import Splash from './Splash.vue'
import C6Logo from './C6Logo.vue'
import ClaroLogo from './ClaroLogo.vue'
import ClaroNetLogo from './ClaroNetLogo.vue'
import NetLogo from './NetLogo.vue'
import OClaro from './OClaro.vue'
import Github from './Github.vue'
import Replay from './Replay.vue'
import Home from './Home.vue'

export default {
  components: { Splash, C6Logo, Replay, Home, ClaroLogo, Github, ClaroNetLogo, NetLogo, OClaro },
  props: {
    name: { type: String, required: true }
  }
}
</script>
