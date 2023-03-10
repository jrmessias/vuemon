<script setup>
import TheFooter from "@/components/TheFooter.vue";
import TheNavbar from "@/components/TheNavbar.vue";</script>

<template>
  <TheNavbar></TheNavbar>
  <div class="main">
    <router-view></router-view>
  </div>
  <TheFooter></TheFooter>
</template>

<style>
</style>
