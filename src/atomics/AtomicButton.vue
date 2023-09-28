<template>
  <button class="AtomicButton">
    <span>{{title}}</span>
  </button>
</template>

<script>
export default {
  name: "AtomicButton",
  props:{
    title: String
  },
}
</script>

<style scoped>
.AtomicButton {

}
</style>