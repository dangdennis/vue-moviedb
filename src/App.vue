<template>
  <div id="app">
    <Header :title="title"/>
    <router-view />
  </div>
</template>

<script>
import Header from "./components/Header.vue";

export default {
    name: "app",
    data() {
        return {
            title: "Dennis",
        };
    },
    components: {
        Header,
    },
};
</script>

<style scoped>
#app {
    font-family: "Avenir", Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #fff;
}
ul li {
    list-style: none;
}

</style>
