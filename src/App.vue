<template>
  <v-app>
    <v-main>
      <router-view />
    </v-main>
  </v-app>
</template>

<script setup>
//
</script>

<style>
html::-webkit-scrollbar {
  width: 5px;
  height: 10px;
}

html::-webkit-scrollbar-thumb {
  background: #545454;
  border-radius: 2px;
}

html::-webkit-scrollbar-track {
  background: #1D1D1D;
  border-radius: 4px;
}

html::-webkit-scrollbar-track:hover,
html::-webkit-scrollbar-track:active {
  background: #14141450;
}
</style>