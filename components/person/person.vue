<template>
    <div>
        <p>{{ name }}</p>
        <p>{{ student }}</p>
    </div>
</template>

<script>
    export default{
        name: 'Person',
        props:{
            name:{
                type: String,
                default: () => ''
            },
            student:{
                type: Boolean,
                require:true
            }
        },
        created(){
            console.log(this.name)
            console.log(this.student)
        }
    }
</script>