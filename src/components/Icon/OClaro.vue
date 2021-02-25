<template>
  <svg :width="size" :height="size" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 181 185">
    <path id="Caminho_21" data-name="Caminho 21" d="M-432.5-723a51.175,51.175,0,0,1-20.046-4.047,51.329,51.329,0,0,1-16.37-11.037,51.33,51.33,0,0,1-11.037-16.37A51.177,51.177,0,0,1-484-774.5a51.176,51.176,0,0,1,4.047-20.046,51.33,51.33,0,0,1,11.037-16.37,51.329,51.329,0,0,1,16.37-11.037A51.176,51.176,0,0,1-432.5-826a51.178,51.178,0,0,1,20.046,4.047,51.329,51.329,0,0,1,16.37,11.037,51.329,51.329,0,0,1,11.037,16.37A51.176,51.176,0,0,1-381-774.5a51.177,51.177,0,0,1-4.047,20.046,51.33,51.33,0,0,1-11.037,16.37,51.33,51.33,0,0,1-16.37,11.037A51.178,51.178,0,0,1-432.5-723Zm0-78A26.53,26.53,0,0,0-459-774.5,26.53,26.53,0,0,0-432.5-748,26.53,26.53,0,0,0-406-774.5,26.53,26.53,0,0,0-432.5-801Z" transform="translate(484 908)" fill="#FFFFFF"/>
    <path id="Caminho_23" data-name="Caminho 23" d="M0,0H22V63H0Z" transform="translate(43)" fill="#FFFFFF"/>
    <path id="Caminho_22" data-name="Caminho 22" d="M0,0H22V84H0Z" transform="translate(149.397 12) rotate(45)" fill="#FFFFFF"/>
    <path id="Caminho_24" data-name="Caminho 24" d="M0,0H22V65H0Z" transform="translate(116 132.5) rotate(-90)" fill="#FFFFFF"/>
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
