# Vue

Right javascript in the way that vue wants you too.

react, angular and vue are some of the main javascript framworks.

Vue front end for the final

main.js is entry point for webpage now
-- probably wont need to come into this file

App.vue file

<template>
html
</template>

<script>
javascript
</script>

<style>
css 
</style>

--all in the same file

using debug tool to spin up client side - - this will run vite

webpage does not need to be refreshed with vite

{{cheese}} -- in template, this will use corresponding js cheese 

v-on:click="mineCheese()"

public stuff should be in the return
private inside the setup

logger.log('cheese went up') --------console.log will break stuff now, so use this now.

let cheese = ref(0) - this will make the cheese more dynamic

cheese.value++ --- .value is necessary to retrieve the value and to change it.

retrieve cheese at appstate
cheese:AppState.cheese-------------Appstate needs to import
---below will be the reactive way to use the AppState.cheese value---
cheese: computed(() => {return AppState.cheese})

doing upgrades variable with in the HomePage.vue return
using computed on upgrades
upgrades: computed(()=> AppState.upgrades)

@click is v-directive of v-on:click wich is a v form of onclick

< span v-if= "autoPower > 0"> ------- this will prevent the span it is in from rendering until autoPower is over 0