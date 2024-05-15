<template>
  <q-tooltip
    @show="onShow"
    class="tooltip bg-transparent q-pa-none"
    :class="`tooltip-arrow-${arrowClass}`"
    ref="tooltipRef"
  >
    <div
      class="tooltip-text text-body1 text-bold relative-position"
      :class="`bg-${bgColor} text-${color}`"
    >
      <slot />
      <q-btn
        v-if="closeable"
        @click="closeTooltip"
        class="tooltip-close absolute-top-right"
        icon="close"
        size="sm"
        flat
        round
        dense
      />
    </div>
    <div
      class="tooltip-arrow absolute"
      :class="`bg-${bgColor}`"
    />
  </q-tooltip>
</template>

<script>
import { computed, ref } from 'vue'

export default {
  props: {
    arrow: {
      type: String,
      default: 'top'
    },
    duration: {
      type: Number,
      default: null
    },
    closeable: {
      type: Boolean,
      default: false
    },
    bgColor: {
      type: String,
      default: 'grey-10'
    },
    color: {
      type: String,
      default: 'white'
    }
  },
  setup(props) {

    /*
      reusables
    */

      const tooltipRef = ref(null)

    /*
      arrow class
    */

      const arrowClass = computed(() => {
        let arrowClassCorrected = props.arrow.replace(' ', '-')
        let allowedClasses = ['top', 'top-left', 'top-right', 'bottom', 'bottom-left', 'bottom-right', 'left', 'left-top', 'left-bottom', 'right', 'right-top', 'right-bottom']
        if (!allowedClasses.includes(arrowClassCorrected)) {
          console.error(`Value "${ arrowClassCorrected }" not allowed for "arrow" prop. Use one of these: `, allowedClasses)
          return 'top'
        }

        return props.arrow.replace(' ', '-')
      })

    
    /*
      event - onShow
    */

      const onShow = () => {
        if (props.duration) {
          setTimeout(() => {
            tooltipRef.value.hide()
          }, props.duration);
        }
      }


    /*
      close tooltip
    */

      const closeTooltip = () => {
        tooltipRef.value.hide()
      }


    /*
      return 
    */

      return {
        arrowClass,
        tooltipRef,
        onShow,
        closeTooltip
      } 

  }
}
</script>

<style lang="scss">
$box-shadow: 0 0 30px 0 rgba(0,0,0,0.5);

.tooltip {
  box-shadow: $box-shadow;
  overflow: visible;
  border-radius: 10px;
  &-text {
    z-index: 10;
    padding: 20px;
    border-radius: 10px;
  }
  &-arrow {
    z-index: 5;
    width: 30px;
    height: 30px;
    box-shadow: $box-shadow;
    transform: translateX(-50%) rotate(-45deg) skew(-20deg, -20deg);

    // top arrows
    [class*="tooltip-arrow-top"] & {
      top: 0px;
    }
    .tooltip-arrow-top & {
      left: 50%;
    }
    .tooltip-arrow-top-left & {
      left: 30px;
    }
    .tooltip-arrow-top-right & {
      right: 0px;
    }

    // bottom arrows
    [class*="tooltip-arrow-bottom"] & {
      bottom: 0px;
    }
    .tooltip-arrow-bottom & {
      left: 50%;
    }
    .tooltip-arrow-bottom-left & {
      left: 30px;
    }
    .tooltip-arrow-bottom-right & {
      right: 0px;
    }

    // left arrows
    [class*="tooltip-arrow-left"] & {
      transform: translateY(-50%) rotate(45deg) skew(-20deg, -20deg);
      left: 0px;
    }
    .tooltip-arrow-left & {
      top: 50%;
    }
    .tooltip-arrow-left-top & {
      top: 20px;
    }
    .tooltip-arrow-left-bottom & {
      bottom: -10px;
    }

    // right arrows
    [class*="tooltip-arrow-right"] & {
      transform: translateY(-50%) rotate(45deg) skew(-20deg, -20deg);
      right: 0px;
    }
    .tooltip-arrow-right & {
      top: 50%;
    }
    .tooltip-arrow-right-top & {
      top: 20px;
    }
    .tooltip-arrow-right-bottom & {
      bottom: -10px;
    }

  }

  // close button
  &-close {
    pointer-events: all !important;
  }
}
</style>