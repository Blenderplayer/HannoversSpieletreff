<template>
  <label
    :class="checkboxClass"
    :style="{'--check': color}"
  >
    <input type="checkbox" :id="checkboxClass" v-model="valueModal"/>
    <label :for="checkboxClass">{{title}}</label>
  </label>
</template>

<script>
export default {
  name: "AtomicCheckboxSimple",
  emits: [],
  props: {
    modelValue: {
      type: Boolean,
      default: false
    },
    checkboxClass: {
      type: String,
      default: 'greenCheckAnimation'
    },
    title: String,
    color: {
      type: String,
      default: 'red'
    }
  },
  data() {
    return {

    }
  },
  computed: {
    valueModal: {
      get(){ return this.modelValue; },
      set(val){ this.$emit('update:modelValue',val); }
    }
  },
  methods: {},
}
</script>

<style scoped>
.AtomicCheckbox {
}
</style>