<template>
  <div class="Tabs">
    <header class="flex flex-row items-center justify-center">
      <div v-for="obj, objIndex in tabs" :key="objIndex" class="Tabs-Header-Item px-6 py-4 mx-3 cursor-pointer" :class="objIndex === activeTab ? 'text-customBlue border-b-4 border-customBlue' : 'border-b'" @click="updateActiveTab(objIndex)">
        {{ obj.title }}
      </div>
    </header>
    <div class="container mx-auto bg-cover lg:bg-contain bg-center bg-no-repeat flex items-center justify-center" :style="`background-image:url(${getActiveTabContent.imgSrc}); min-height: 600px;`">
      <div class="mb-16 text-white">
        <h2 class="text-4xl uppercase text-center font-bold mb-4">{{ getActiveTabContent.title }}</h2>
        <div class="bg-white h-2 w-16 mx-auto mb-16" />
        <p class="text-center mx-8 lg:mx-24">{{ getActiveTabContent.description }}</p>
      </div>
    </div>
  </div>
</template>

<script>
import { reactive, toRefs, computed } from 'vue'
import Inside from '../assets/inside.png';

export default {
  setup() {
    const data = reactive({
      activeTab: 0,
      getActiveTabContent: computed(() => {
        return data.tabs[data.activeTab]
      }),
      tabs: [{
        imgSrc: Inside,
        title: 'Design',
        description: 'From the outside, it is a mere formality to quickly identify a Porsche as such. And in the interior, you can also sense distinctive Porsche genes in the new Taycan. The basic features of the interior architecture are sporty, minimalist and clear; the wing extending from the centre console catches your eye and appears to be floating. The innovative cockpit displays are clearly driver-oriented, allowing you to keep an eye on the most important information, even during dynamic driving.'
      }, {
        imgSrc: Inside,
        title: 'Performance',
        description: 'The Porsche soul stands for performance. In every respect. As demonstrated by the Taycan, even when charging: its 800-volt architecture produces charge power of up to 270kW. In five minutes, the Taycan Turbo, for example, can be charged to enable a range of up to 100km (WLTP) under optimum conditions¹ and is always ready for what its driver spends the whole day dreaming about: driving.'
      }, {
        imgSrc: Inside,
        title: 'Charging',
        description: 'We instantly know what is good for our soul – and what inspires it. The Taycan reveals its fascination within fractions of a second: with a fluid yet sharp silhouette and a dynamic flyline. Its rear design boasts a seamless light strip and ‘PORSCHE’ logo made of three-dimensional letters in a glass look. Seen enough? Definitely not.'
      }, {
        imgSrc: Inside,
        title: 'Comfort',
        description: 'We never forget the most breathtaking experiences of our life. The Taycan interior is also impressive. The GT multifunction sports steering wheel¹ and the deep, sporty seating position heighten your anticipation of the journey ahead long before you set off. The Porsche Advanced Cockpit with its innovative curved display also focuses on state-of-the-art comfort – tailor-made for an electrifying driving experience that will last forever.'
      }]
    })

    const updateActiveTab = (objIndex) => {
      data.activeTab = objIndex
    }

    return {
      updateActiveTab,
      ...toRefs(data)
    }
  }
}
</script>