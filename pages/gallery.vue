<template>
    <div>
      <BigImg :image="img" @rm="runModal($event)"/>
      <Thumb :images="items" @selectedImg="showImg($event)"/>
      <Modal v-show="showModal" :image="img" :images="items" @selectedImg="showImg($event)"  @closeModel="runModal($event)"/>
      
    </div>
  </template>
  
  <script>
  import TopNav from '../components/nav/TopNav.vue'
  import Thumb from '../components/gallery/thumbs.vue'
  import BigImg from "~/components/gallery/bigImage.vue";
  import Modal from "~/components/modals/modal.vue";
  
  export default {
    name: 'GalleryPage',
    components: {BigImg, TopNav, Thumb, Modal},
    data() {
      return {
        items: [
          'https://img.freepik.com/premium-zdjecie/meski-zegarek-mechaniczny-na-ciemnym-tle_488220-26725.jpg?size=626&ext=jpg&uid=R97524322&semt=sph',
          'https://img.freepik.com/darmowe-zdjecie/strzal-w-skali-szarosci-czarny-zegarek_181624-422.jpg?size=626&ext=jpg&uid=R97524322&semt=sph',
          'https://img.freepik.com/darmowe-zdjecie/urzadzenie-cyfrowe-z-ekranem-zegarka_53876-97321.jpg?size=626&ext=jpg&uid=R97524322&semt=sph'
        ],
  
        img: 'https://img.freepik.com/premium-zdjecie/meski-zegarek-mechaniczny-na-ciemnym-tle_488220-26725.jpg?size=626&ext=jpg&uid=R97524322&semt=sph',
        showModal : false
      }
    },
  
    methods: {
      showImg(url) {
        this.img = url
        console.log(url)
      },
      runModal(e) {
        console.log(e)
        this.showModal = e
      }
    }
  }
  </script>
  