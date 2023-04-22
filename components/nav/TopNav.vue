<template>
  <div class="nav" ref="topElement">
    <NuxtLink class="nav-item" to="/about">About</NuxtLink>
    <NuxtLink class="nav-item" to="/">Home</NuxtLink>
    <NuxtLink class="nav-item" to="/gallery">Gallery</NuxtLink>
    <NuxtLink class="nav-item" to="/cars/">Car</NuxtLink>
    <NuxtLink class="nav-item" to="/nasa/">NASA</NuxtLink>

  </div>
</template>
  
<script>
export default{
  name:"Top",
  data(){
    return{
      name:'123'
    }
  }
}
</script>

<style scoped>
.nav {
  display: flex;
  width: 100vw;
  color: white;
  height: 100px;
  background-color: rgb(24, 68, 112);
  justify-content: center;
  align-items: center;
 
}

.nav-item {
  padding: 0 10px;
  text-decoration: none;
  color: white;
}

.nuxt-link-exact-active,.nav-item:hover {
  color: rgb(240, 52, 52);
}
</style>