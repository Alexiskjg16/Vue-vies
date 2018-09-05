<template>
  <div class="hello">
    <h1> What Movie Are You Looking For? </h1>
    <h1>Search By Keyword:</h1>
      <input v-model="search" type=text>
			<button v-on:click="searching">Search</button>
    <h1> Results: </h1>
  <ul>
        <li v-for="movie in movies" v-bind:key="movie.id">
            <img :src="getImageURL(movie.poster_path)" alt=""> 
            <header>{{movie.title}}</header>
            <header>Released:{{movie.release_date}}</header>
        </li>  
    </ul>
  </div>
</template>

<script>
export default {
  name: "MovieList",
  data: function() {
    return {
      movies: [],
      search: ""
    };
  },
  methods: {
    searching: function() {
      console.log(this.search);
      const URL = `https://api.themoviedb.org/3/search/movie?api_key=e68c1a67b9b6a0fff17d9ed980ca72cf&language=en-US&query=${
        this.search
      }&page=1&include_adult=false`;
      fetch(URL)
        .then(resp => resp.json())
        .then(json => {
          console.log(json);
          this.movies=json.results
        });
    },
    getImageURL(poster_path) {
      return "https://image.tmdb.org/t/p/w500/" + poster_path;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
  background-color: rgba(100, 10, 60);
}
ul {
  list-style-type: none;
  padding: 0;
  margin: 2em;
  margin-bottom: 10px;
  background-color: rgba(100, 10, 60);
}
li {
  display: inline-block;
  margin: 10px;
  background-color: rgba(100, 10, 60);
}
img {
  width: 15em;
  height: auto;
}
</style>
