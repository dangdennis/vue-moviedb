<template>
    <header>
        <h1><router-link to="/">{{ title }}</router-link></h1>
        <transition name="fade">
            <h1 v-if="show">Animated</h1>
        </transition>
        <button @click="show = !show">Show/Hide</button>
    </header>
</template>

<script>
export default {
    name: "Header",
    props: {
        title: String,
    },
    data() {
        return {
            show: false,
            name: "Vue That Movie",
        };
    },
    computed: {},
};
</script>

<style scoped>
header {
    background-color: #111;
    padding: 20px;
    color: white;
}
h1 {
    margin: 0;
}

.fade-enter-active,
.fade-leave-active {
    transition: all 0.3s ease-out;
}

.fade-enter,
.fade-leave-to {
    opacity: 0;
    transform: scale(0);
}

/* name-enter -> name-enter-to */
/* name-enter-active */

/* name-leave -> name-leave-to */
/* name-leave-active */
</style>