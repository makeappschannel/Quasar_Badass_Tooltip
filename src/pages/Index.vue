<template>
  <q-page class="q-pa-md">

    <div class="text-h5">Top Arrows</div>

    <q-btn
      label="Top arrow"
      color="primary"
      class="q-ma-lg"
    >
      <tooltip
        arrow="top"
      >
        I am so badass
      </tooltip>
    </q-btn>
    
    <q-btn
      label="Top left arrow"
      color="primary"
      class="q-ma-lg"
    >
      <tooltip
        arrow="top left"
      >
        I am so badass
      </tooltip>
    </q-btn>

    
    <q-btn
      label="Top right arrow"
      color="primary"
      class="q-ma-lg"
    >
      <tooltip
        arrow="top right"
      >
        I am so badass
      </tooltip>
    </q-btn>

    <div class="text-h5 q-mt-lg">Bottom Arrows</div>

    <q-btn
      label="Bottom arrow"
      color="primary"
      class="q-ma-lg"
    >
      <tooltip
        arrow="bottom"
        anchor="top middle"
        self="bottom middle"
      >
        I am so badass
      </tooltip>
    </q-btn>

    <q-btn
      label="Bottom left arrow"
      color="primary"
      class="q-ma-lg"
    >
      <tooltip
        arrow="bottom left"
        anchor="top middle"
        self="bottom middle"
      >
        I am so badass
      </tooltip>
    </q-btn>

    <q-btn
      label="Bottom right arrow"
      color="primary"
      class="q-ma-lg"
    >
      <tooltip
        arrow="bottom right"
        anchor="top middle"
        self="bottom middle"
      >
        I am so badass
      </tooltip>
    </q-btn>

    <div class="text-h5 q-mt-lg">Left & Right Arrows</div>

    <q-btn
      label="Left arrow"
      color="primary"
      class="q-ma-lg"
    >
      <tooltip
        arrow="left"
        anchor="center end"
        self="center start"
      >
        I am so badass
      </tooltip>
    </q-btn>

    <q-btn
      color="primary"
      class="q-ma-lg"
    >
      Left<br>top arrow
      <tooltip
        arrow="left top"
        anchor="center end"
        self="top start"
      >
        I am<br>so badass
      </tooltip>
    </q-btn>

    <q-btn
      color="primary"
      class="q-ma-lg"
    >
      Left<br>bottom arrow
      <tooltip
        arrow="left bottom"
        anchor="center end"
        self="bottom start"
      >
        I am<br>so badass
      </tooltip>
    </q-btn>

    <q-btn
      label="Right arrow"
      color="primary"
      class="q-ma-lg"
    >
      <tooltip
        arrow="right"
        anchor="center start"
        self="center end"
      >
        I am so badass
      </tooltip>
    </q-btn>

    <q-btn
      color="primary"
      class="q-ma-lg"
    >
      Right<br>top arrow
      <tooltip
        arrow="right top"
        anchor="center start"
        self="top end"
      >
        I am<br>so badass
      </tooltip>
    </q-btn>

    <q-btn
      color="primary"
      class="q-ma-lg"
    >
      Right<br>bottom arrow
      <tooltip
        arrow="right bottom"
        anchor="center start"
        self="bottom end"
      >
        I am<br>so badass
      </tooltip>
    </q-btn>

    <div class="text-h5 q-mt-lg">Programmatically Triggered</div>

    <q-btn
      @click="showTooltip = !showTooltip"
      label="Click to toggle Tooltip"
      color="primary"
      class="q-ma-lg"
    >
      <tooltip
        v-model="showTooltip"
        arrow="top"
        no-parent-event
      >
        I am so badass
      </tooltip>
    </q-btn>

    <q-btn
      @click="showTooltipWithHide = true"
      label="Hide Tooltip after delay"
      color="primary"
      class="q-ma-lg"
    >
      <tooltip
        v-model="showTooltipWithHide"
        arrow="top"
        no-parent-event
        :duration="2000"
      >
        I am so badass
      </tooltip>
    </q-btn>

    <q-btn
      @click="showTooltipWithClose = true"
      label="Show Tooltip with Close Button"
      color="primary"
      class="q-ma-lg"
    >
      <tooltip
        v-model="showTooltipWithClose"
        arrow="top"
        no-parent-event
        closeable
      >
        I am so badass
      </tooltip>
    </q-btn>

    <div class="text-h5 q-mt-lg">Custom Colors!</div>

    <q-btn
      label="White and black"
      color="primary"
      class="q-ma-lg"
    >
      <tooltip
        arrow="top"
        bg-color="white"
        color="black"
      >
        I am so badass
      </tooltip>
    </q-btn>

    <q-btn
      label="White and pink"
      color="primary"
      class="q-ma-lg"
    >
      <tooltip
        arrow="top"
        bg-color="white"
        color="pink"
      >
        I am so badass
      </tooltip>
    </q-btn>

    <q-btn
      label="Red and white"
      color="primary"
      class="q-ma-lg"
    >
      <tooltip
        arrow="top"
        bg-color="red"
        color="white"
      >
        I am so badass
      </tooltip>
    </q-btn>

    <q-btn
      label="Purple and white"
      color="primary"
      class="q-ma-lg"
    >
      <tooltip
        arrow="top"
        bg-color="purple"
        color="white"
      >
        I am so badass
      </tooltip>
    </q-btn>

    <q-btn
      label="Primary"
      color="primary"
      class="q-ma-lg"
    >
      <tooltip
        arrow="top"
        bg-color="primary"
        color="white"
      >
        I am so badass
      </tooltip>
    </q-btn>

    <q-btn
      label="Secondary"
      color="primary"
      class="q-ma-lg"
    >
      <tooltip
        arrow="top"
        bg-color="secondary"
        color="white"
      >
        I am so badass
      </tooltip>
    </q-btn>

    <q-btn
      label="Positive"
      color="primary"
      class="q-ma-lg"
    >
      <tooltip
        arrow="top"
        bg-color="positive"
        color="white"
      >
        I am so badass
      </tooltip>
    </q-btn>

    <q-btn
      label="Negative"
      color="primary"
      class="q-ma-lg"
    >
      <tooltip
        arrow="top"
        bg-color="negative"
        color="white"
      >
        I am so badass
      </tooltip>
    </q-btn>

  </q-page>
</template>

<script>
import { defineComponent, ref } from 'vue';

export default defineComponent({
  name: 'PageIndex',
  setup() {
    let showTooltip = ref(false)
    let showTooltipWithHide = ref(false)
    let showTooltipWithClose = ref(false)

    return {
      showTooltip,
      showTooltipWithHide,
      showTooltipWithClose,
    }
  },
  components: {
    'tooltip': require('components/Tooltip').default
  }
})
</script>
