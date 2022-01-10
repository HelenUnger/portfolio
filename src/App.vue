<template>
    <div id="app" :class="darkMode ? 'dark-mode' : 'day-mode'">
        <Nav @dark-mode="toggleDarkMode($event)" />
        <Header/>
        <Skills />
        <About />
    </div>
</template>

<script>
import Nav from './components/navigation.vue'
import Header from './components/header.vue'
import Skills from './components/skills.vue'
import About from './components/about.vue'

export default {
    name: 'App',

    components: {
        Nav,
        Header,
        Skills,
        About
    },

    data() {
        return {
            darkMode: true,
        };
    },

    methods: {
        toggleDarkMode(event) {
            this.darkMode = event;
        }
    }
};
</script>

<style lang="scss">
body {
    margin: 0;
}

#app {
    max-width: 100vw;
    min-height: 100vh;
    overflow: hidden;
}

.day-mode {
    background-color: #fff;
    color: #343a40;
    transition: all 0.2s linear;
}

.dark-mode {
    background-color: #343a40;
    color: #fff;
    transition: all 0.2s linear;
}
</style>
