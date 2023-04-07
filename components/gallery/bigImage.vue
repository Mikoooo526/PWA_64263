<template>
  <div class="bigImg">
    <img :src="image" class="img-item" @click="showModal"/>
  </div>
   
</template>
<script>
export default {
  name: 'BigImage',
  props: {
    image: {
      type: String,
      default: () => ''
    }
  },
  methods: {
    showModal() {
      this.$emit('rm', true)
    }
  }
}
</script>
<style scoped>
.bigImg {
  display: flex;
  justify-content: center;
  margin-top: 100px;
}

.img-item {
  max-height: 350px;
  cursor: pointer;
}

</style>