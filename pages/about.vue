<template>
    <div>
        <!-- <h1 class="colorRed">About</h1>
        <button @click="showInfo">Kliknij mnie</button> -->
        <h1>Gallery</h1>
        <BigImage image="https://img.freepik.com/darmowe-zdjecie/zolty-zonkil-narcyz-kwitnacy-w-ogrodzie_127675-2729.jpg?w=826&t=st=1679759619~exp=1679760219~hmac=16bc530ed103e815ea90b0515168ca251845e2dcf4822f3f3cba293d01b28582"/>
        
    </div>
</template>

<script>
import BigImage from '~/components/gallery/bigImage.vue';
import TopNav from '../components/nav/TopNav.vue';
export default {
  name: 'AboutPage',
  components: { TopNav, BigImage },

  // methods: {
  //   showInfo: () => { 
  //       console.log('Witaj w konsoli')
  //       return alert('Witaj') 
  //   }
  // }
}
</script>
<style scoped>
.colorRed {
    color: red;
}

</style>