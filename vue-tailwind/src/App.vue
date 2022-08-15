<template>
    <nav-view/>
    <card-view/>
    <card-view/>
    <card-view/>
    <card-view/>
</template>

<script>
import Header from './components/HeaderView.vue'
import Card from './components/CardView.vue'
export default {
   components:{
      "card-view":Card,
      "nav-view":Header
   }
}
</script>

<style>

</style>