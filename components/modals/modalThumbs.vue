<template>
    <div class="modal" @click="closeModal">
        <div class="modal-content">
            <img :src="image" class="BigImage">
            <div class="thumb">
                <img :src="item" v-for="(item, index) in images" :key="index" class="image" @click="sendImage(item)">
            </div>
        </div>
    </div>
</template>
  
<script>


export default {
    name: 'Modal',
    props: {
        image: {
            type: String,
            default: () => ''
        },
        images: {
            type: Array,
            default: () => []
        }
    },

    methods: {
        closeModal() {
            this.$emit('closeModel', false)
        },
        sendImage(url) {
            this.$emit('selectedImg', url)
        }
    }
}

</script>
<style scoped>
.modal {
    display: flex;
    position: absolute;
    left: 0;
    top: 0;
    width: 100vw;
    height: 100vh;
    background-color: rgba(0, 0, 0, 0.7);
}

.modal-content {
    background-color: white;
    width: 900px;
    height: 725px;
    justify-content: center;
    align-items: center;
    position: absolute;
    left: calc(50vw - 433px);
    top: calc(50vh - 300px);
}

.BigImage {
    position: absolute;
    left: 50vh;
    top: 25vh;
    transform: translate(-50%, -50%);
}

.thumb {
    margin-top: 500px;
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
  