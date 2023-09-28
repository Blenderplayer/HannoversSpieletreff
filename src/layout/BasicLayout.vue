<template>
    <div
        class="basicGrid"
        :style="mainLayerStyle"
    >
        <div class="wave"></div>
        <div class="wave"></div>
        <div class="wave"></div>
      <div
          v-if="$slots.background"
          :class="[gridClasses?.background, gridClasses?.default]"
          class="backgroundMain"
      >
        <slot name="background"></slot>
      </div>
      <div
            v-if="$slots.header"
            :class="[gridClasses?.header, gridClasses?.default]"
            style="grid-area: header"
            :style="[mainLayerStyle, directionStyle]"
        >
            <slot name="header"></slot>
        </div>
        <div
            v-if="$slots.main"
            :class="[gridClasses?.main, gridClasses?.default]"
            style="grid-area: main"
            :style="[mainLayerStyle, directionStyle]"
        >
            <slot name="main"></slot>
        </div>
        <div
            v-if="$slots.footer"
            :class="[gridClasses?.footer, gridClasses?.default]"
            style="grid-area: footer"
            :style="[mainLayerStyle, directionStyle]">
            <slot name="footer"></slot>
        </div>
        <div
            v-if="$slots.leftside"
            :class="[gridClasses?.leftside, gridClasses?.default]"
            style="grid-area: leftside"
            :style="[overlayLayerStyle, directionStyle]"
        >
            <slot name="leftside" class="leftside"></slot>
        </div>
        <div
            v-if="$slots.rightside"
            :class="[gridClasses?.rightside, gridClasses?.default]"
            style="grid-area: rightside"
            :style="[overlayLayerStyle, directionStyle]"
        >
            <slot name="rightside" class="rightside"></slot>
        </div>
        <div
            v-if="$slots.overlay"
            :class="[gridClasses?.overlay, gridClasses?.default]"
            class="overlayMain"
            :style="[overlayLayerStyle, directionStyle]"
        >
            <slot name="overlay"></slot>
        </div>
    </div>
</template>

<script>

export default {
    name: "BasicLayout",
    props: {
        layerIndex: {
            type: Number,
            default: 1
        },
        direction: {
            type: String,
            default: 'center'
        },
        gridClasses: {
            type: Object,
            nullable: true
        }
    },
    data() {
        return {
            mainLayerStyle: {
                zIndex: this.layerIndex
            },
            overlayLayerStyle: {
                zIndex: this.layerIndex + 20
            },
            directionStyle: {
                textAlign: this.direction
            }
        }
    }
}
</script>

<style scoped>
.basicGrid {
    position: relative;
    display: grid;
    grid-template: "header header header" "leftside main rightside" "footer footer footer";
    grid-template-columns: 1fr 3fr 1fr;
    grid-template-rows: auto 100% auto;
    z-index: 1;
}

.backgroundMain {
  position: absolute;
  top: 0;
  right: 0;
  height: 100%;
  width: 100%;
  z-index: -20;
}

.overlayMain {
    position: absolute;
    top: 0;
    right: 0;
    height: 100%;
    width: 100%;
    z-index: 20;
}

</style>