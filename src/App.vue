

<script setup>
  import {  RouterView } from 'vue-router'; 
  import NavComp from './components/NavComp.vue';
</script>

<template>
  <NavComp/>
  
  <RouterView/>
</template>

<style>
  h1 {
    color: black;
  }
</style>