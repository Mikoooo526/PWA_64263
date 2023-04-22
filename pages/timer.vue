<template>
    <div>
        <Timer targetDate='2023-04-27 20:45:00'/>
    </div>
</template>

<script>
import BigImage from '~/components/gallery/bigImage.vue';
import TopNav from '../components/nav/TopNav.vue';
import Timer from '../components/gallery/timer.vue';
export default {
  name: 'AboutPage',
  components: { TopNav, BigImage,Timer },

  methods: {
    showInfo: () => { 
        console.log('Witaj w konsoli')
        return alert('Witaj') 
    }
  }
}
</script>
<style scoped>
.colorRed {
    color: red;
}
</style>