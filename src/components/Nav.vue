<template>
  <div class="Nav container mx-auto my-8 grid grid-flow-col grid-cols-1 md:grid-cols-2 gap-4">
    <div>
      <img :src="PorscheLogo" alt="Porsche logo" class="w-16 mx-auto md:mx-0" />
    </div>
    <div class="hidden md:block">
      <div class="grid grid-flow-col grid-cols-7 gap-4 items-center h-full">
        <p v-for="option, optionIndex in menu" :key="optionIndex" @click="openLink(option.link)" class="cursor-pointer text-xs font-bold">{{ option.title }}</p>
      </div>
    </div>
    <div class="block md:hidden fixed right-8 top-8 cursor-pointer" @click="openMenu">
      <img :src="MenuIcon" alt="Display menu" class="w-6" />
    </div>
  </div>
</template>

<script setup>
import MenuIcon from '../assets/menu.png'
import PorscheLogo from '../assets/porsche_logo.png'

const menu = [{
 title: 'Brand',
 link: '' 
}, {
 title: '718',
 link: '' 
}, {
 title: '911',
 link: '' 
}, {
 title: 'Taycan',
 link: '' 
},{
 title: 'Macan',
 link: '' 
}, {
 title: 'Panamera',
 link: '' 
}, {
 title: 'Cayenne',
 link: '' 
}]

const openLink = (link) => {
  window.open(link)
}

const openMenu = () => {
  console.log('open menu')
}
</script>