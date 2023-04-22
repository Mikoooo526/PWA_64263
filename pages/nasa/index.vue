<template>
    <div>
        <h1>Nasa</h1>
        <input v-model="message" placeholder="Search...">
        <button @click="$event =>find()">Search</button>
        <div style="display: flex; flex-wrap: wrap; width: 100vw; justify-content: center">
            <img :src="value.links[0].href" v-for="(value, index) in dataArr" :key="index"
                style="width: 100px; height: 100px; object-fit: cover; padding: 5px" />
        </div>

    </div>
</template>
    
<script>
import axios from "axios";
export default {
    name: "index",

    created() {
        this.fetchData("sun")
    },

    data() {
        return {
            dataArr: [],
            message:""
        }
    },

    methods: {
        find(){
            this.fetchData(this.message);
            this.message = ""
        },
        async fetchData(search) {
            await axios.get('https://images-api.nasa.gov/search?q=' + search) 
                .then(res => {
                    this.dataArr = res.data.collection.items;
                })
                .catch(error => {
                    console.log(error)
                })
        }
    }
}
</script>
    
<style scoped></style>