<template>
  <div
      class="movie-card position-absolute"
      :style="randomPosition"
  >
    <div :style="randomStyle" class="rotation-animation">
      <div class="frontofcard">
        <div class="image"><img :src="`card${this.image}.png`" alt="" srcset=""></div>
      </div>
      <div class="backofcard">
        <div class="image"><img src="card2.png" alt="" srcset=""></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Card",
  data(){
    return {
      image: 1+Math.floor(Math.random()*14),
      translate: {
        x: (Math.random()*200)-50,
        y: -Math.random()*100-100,
        delay: Math.random()*10
      },
      rotation: Math.random()*360,
      scale: (Math.random()*0.5)+0.1,
    }
  },
  computed: {
    randomPosition(){
      return `left:${this.translate.x}%; top:${this.translate.y}vh; animation-delay: ${this.translate.delay}s;`
    },
    randomStyle(){
      return `transform: rotateX(${this.rotation}deg) rotateY(${this.rotation}deg) scale(${this.scale})`
    }
  },
}
</script>

<style scoped>
</style>