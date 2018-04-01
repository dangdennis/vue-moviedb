<template>
    <ul>
        <li :key="movie" v-for="movie in movies">
            <Movie :movie="movie" />
        </li>
    </ul>
</template>

<script>
import Movie from "./Movie.vue";

export default {
    name: "MoviesList",
    data() {
        return {
            movies: [],
        };
    },
    created: function() {
        this.fetchData();
    },
    methods: {
        fetchData: async function() {
            try {
                const result = await fetch(
                    `https://api.themoviedb.org/3/discover/movie?sort_by=popularity.desc&api_key=846bf0d4b88397f4c9c137322395d3a4`,
                );
                const movies = await result.json();
                this.movies = movies.results;
            } catch (e) {
                console.log(e);
            }
        },
    },
    components: {
        Movie,
    },
};
</script>

<style scoped>
ul {
    display: grid;
    list-style: none;
    padding: 1rem;
    margin: 0;
    grid-gap: 1rem;
    grid-template: auto / repeat(auto-fit, minmax(150px, 1fr));
}
</style>