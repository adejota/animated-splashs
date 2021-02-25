<template>
  <svg xmlns="http://www.w3.org/2000/svg" width="178.142" height="42.402" viewBox="0 0 178.142 42.402">
    <path id="N" fill="none" stroke="#fff" stroke-width="7.2" d="M1089.168,1215.111v-38.789h4.1l27.09,34.934h4.1v-38.071" transform="translate(-1085.568 -1172.722)"/>
    <path id="Linha_superior" d="M1137.316,1216.462h75.09" fill="none" stroke="#fff" stroke-width="7"/>
    <path id="Sombra_superior" d="M1696.486,354.246c-42.455,7.181-75.17,0-75.17,0Z" transform="translate(-1569.884 -347.068)"/>
    <path id="Linha_meio" fill="none" stroke="#fff" stroke-width="7" d="M1137.316,1216.462h75.09" transform="translate(-1085.679 -1195.284)"/>
    <path id="Sombra_inferior" d="M1696.486,354.246c-42.455,7.181-75.17,0-75.17,0Z" transform="translate(1748.234 389.515) rotate(180)"/>
    <path id="Linha_inferior" d="M1137.316,1216.462h75.09" fill="none" stroke="#fff" stroke-width="7"/>
    <path id="T_direita" fill="none" stroke="#fff" stroke-width="7.2" d="M1263.71,1176.43h-21.094" transform="translate(-1085.568 -1172.722)"/>
    <path id="T_centro" fill="none" stroke="#fff" stroke-width="7.2" d="M1242.708,1176.43v38.695" transform="translate(-1085.568 -1172.722)"/>
    <path id="T_esquerda" fill="none" stroke="#fff" stroke-width="7.2"  d="M1221.707,1176.43h21.38" transform="translate(-1085.568 -1172.722)"/>
  </svg>
</template>

<script>
export default {
  props: {
    size: { type: [String, Number], default: 22 },
    color: { type: String, default: 'white' }
  }
}
</script>

<style lang="postcss" scoped>
@keyframes undrawN {
  to {
    stroke-dashoffset: 400;
  }
}

#N {
  stroke-dasharray: 400;
  stroke-dashoffset: 0;
  animation: undrawN 1.5s linear forwards;
  animation-delay: 1s;
}

@keyframes undrawTX {
  to {
    stroke-dashoffset: 200;
  }
}

#T_direita {
  stroke-dasharray: 200;
  stroke-dashoffset: 0;
  animation: undrawTX 2s linear forwards;
  animation-delay: 0.2s;
}

#T_esquerda {
  stroke-dasharray: 200;
  stroke-dashoffset: 0;
  animation: undrawTX 2s linear forwards;
  animation-delay: 0.2s;
}

@keyframes undrawTY {
  to {
    stroke-dashoffset: 300;
  }
}

#T_centro {
  stroke-dasharray: 300;
  stroke-dashoffset: 0;
  animation: undrawTY 2s linear forwards;
  animation-delay: 0.4s;
}

@keyframes translateDown {
  to {
    transform: translate(-1085.679px, -1195.754px);
  }
}

#Linha_superior {
  transform: translate(-1085.679px, -1212.754px);
  stroke-dasharray: 200;
  stroke-dashoffset: 0;
  animation: translateDown 1s ease-in-out 2s forwards, undrawLinhas 1s linear 2.2s forwards;
}

@keyframes translateUp {
  to {
    transform: translate(-1085.679px, -1195.684px);
  }
}

#Linha_inferior {
  transform: translate(-1085.679px, -1177.684px);
  stroke-dasharray: 200;
  stroke-dashoffset: 0;
  animation: translateUp 1s ease-in-out 2s forwards, undrawLinhas 1s linear 2.2s forwards;

}

@keyframes vanishShadows {
  to {
    fill: none;
  }
}

#Sombra_superior, #Sombra_inferior {
  fill: #60bbea;
  animation: vanishShadows 1s linear forwards;
  animation-delay: 1.65s;
}

@keyframes undrawLinhas {
  to {
    stroke-dashoffset: 200;
  }
}

#Linha_meio {
  stroke-dasharray: 200;
  stroke-dashoffset: 0;
  animation: undrawLinhas 1s linear forwards;
  animation-delay: 2.2s;
}
</style>
