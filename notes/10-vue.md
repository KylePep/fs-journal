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


<!-- SECTION TUESDAY -->

<!-- STUB API KEY -->
adding an Api Key to your searches


Axios Service => 
                      export const movieApi = Axios.create({
                        baseURL:,  
                        timeout: 8000
                        params: {
                          api_key: '**(The api key value- long string)**'
                          include_adult: false,
                          certification_country: 'US',
                          'certification.get': 'G',
                          'certification.lte': 'PG-13'
                        }
                      })


HomePage.vue
----starting spot
----emptied out home page ** the vt snippet we added**

LifeCycle hooks 
onMountded, onUpdated, onUnmounted

on model
  this.poster = `https:/image.sdklfjslkdfj;askdjfas;df/${data.poster_path}` ------with the string path and interpolation you can use this to get the image with out having to do something complicated elsewhere

  Service
  const movies = res.data.results.map(moviePjo => new Movie(moviewPojo))
  AppState.movies = movies

<!-- STUB movies variable -->
invoked the movies array from the appstate with {{ movies }} in the html
return {
  movies: computed( () => AppState.movies)
}

<!-- STUB iterate over data -->
<h2 v-for="movie in movies" :key="movie.id">
{{movie.title}}
</h2>

<!-- STUB image iteration -->
<img :src="movie.poster" :alt="movie.title">

<!-- STUB component iteration -->
utilized when v-for-ing over a collection and using a componenent. props are on the child, components and computed are on the parent

<h2 v-for="movie in movies" :key="movie.id" class="col-3"> 
<img :src="movieProp.poster" :alt="movieProp.title">
<MovieCard :movieProp="movie"/>
</h2>

MovieCard.vue
inside javascript section inside export default{} outside of setup(){}
props:{
  movieProp: {type: Movie, required: true}
}