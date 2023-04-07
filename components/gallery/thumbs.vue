<template>
    <div class="thumb">
          <img :src="item" v-for="(item, index) in images" :key="index" class="image" @click="sendImage(item)">
    </div>
  </template>
  
  <script>
  export default {
    name: 'Thumb',
    props: {
      images: {
        type: Array,
        default: () => []
      }
    },
  
    created() {
      // console.log(this.images)
    },
  
    methods: {
      sendImage(url) {
        this.$emit('selectedImg', url)
      }
    }
  }
  </script>
  <style scoped>
  .thumb {
    margin-top: 10px;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .image {
    width: 150px;
    height: 150px;
    padding: 10px 5px;
    cursor: pointer;
  }
  .image:hover {
    border: 1px solid green;
  }
  </style>
  