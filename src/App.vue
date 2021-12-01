<template>
    <div id="app">
        <vipList/>
    </div>
</template>
<script>
import vipList from './components/vipList.vue'

export default {
   name: "App",
   components: {
       vipList
        
    },
}
</script>

<style>
#app {
    font-family: Arial, Helvetica, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: black;
    margin-top: 60px;
}

</style>
