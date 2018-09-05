<template>
  <div id="app">
    <h1> {SearchTheFilm.com} </h1>
    <section>
    <img src="./components/grunge-strip.jpeg" />
    <img src="./components/grunge-strip.jpeg" />
    <img src="./components/grunge-strip.jpeg" />
    <img src="./components/grunge-strip.jpeg" />
    <img src="./components/grunge-strip.jpeg" />
    <img src="./components/grunge-strip.jpeg" />
    <img src="./components/grunge-strip.jpeg" />
    <img src="./components/grunge-strip.jpeg" />
    </section>
    <MovieList />
  </div>
</template>

<script>
import MovieList from './components/MovieList.vue'

export default {
  name: 'app',
  components: {
    MovieList,
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #000000;
  margin-top: 60px;
  background-color: rgba(100, 10, 60);
}

section {
  display: flex;
  flex-direction: row;
}
img {
  display: flex;
  justify-content:flex-start;
  height: 7em;
}

</style>
