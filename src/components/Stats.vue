<template>
  <div class="Stats bg-cover bg-no-repeat bg-bottom relative py-8 lg:pt-32" :style="`background-image:url(${PorscheBackground}); min-height: 300px; margin-bottom: 300px; background-position: center bottom -6rem;`">
    <div class="w-full h-full bg-customBlue lg:opacity-75 absolute top-0 left-0 z-0" />
    <div class="Stats-Components flex flex-col lg:flex-row items-center justify-between w-full z-50 relative lg:absolute p-8">
      <stats-card v-for="obj, objIndex in cards" :key="objIndex" :content="obj" />
    </div>
  </div>
</template>

<script>
import { reactive, toRefs } from 'vue'
import Plug from '../assets/rounded-plug.png';
import Size from '../assets/dimensions.png';
import Speed from '../assets/speed.png';
import Weight from '../assets/weight.png';
import StatsCard from '../components/elements/stats/StatsCard.vue'
import PorscheBackground from '../assets/2020-porsche.jpeg';

export default {
  components: {
    StatsCard
  },
  setup() {
    const data = reactive({
      PorscheBackground,
      cards: [{
        imgSrc: Plug,
        title: "Range",
        description: "301 miles<br>(25.4 - 20.4 kWh/100 miles)"
      },{
        imgSrc: Speed,
        title: "Speed",
        description: "5.4s<br>0 - 100km"
      },{
        imgSrc: Size,
        title: "Size",
        description: "L: 4,963 mm<br>W: 1,966 mm<br>H: 1,395 mm"
      },{
        imgSrc: Weight,
        title: "Weight",
        description: "2,050 kg"
      }]
    })

    return {
      ...toRefs(data)
    }
  }
}
</script>