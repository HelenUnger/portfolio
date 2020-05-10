<template>
    <div class="navigation-container">
        <div class="text-right d-md-none">
            <span @click="toggleMode()">
                NIGHT/DAY
            </span>
            <span class="d-inline p-2" @click="toggleNav()">
                =
            </span>
        </div>
        <div :class="['nav', {'open': openNav}]">
            <div class="text-right d-md-none">
                <span class="d-inline p-2" @click="toggleNav()">
                    =
                </span>
            </div>
            <div class="nav-links">
                <a class="nav-link" href="#">Home</a>
                <a class="nav-link" href="#">Skills</a>
                <a class="nav-link" href="#">My Work</a>
                <a class="nav-link" href="#">Contact</a>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        darkMode: {
            type: Boolean,
            required: true
        },
    },

    data() {
        return {
            openNav: false,
            localDarkMode: false
        };
    },

    methods: {
        toggleNav() {
            this.openNav = !this.openNav;
        },
        toggleMode() {
            this.localDarkMode = ! this.darkMode;
            this.$emit('dark-mode', this.localDarkMode);
        }
    }
}
</script>
<style lang="scss" scoped>
    .navigation-container {
        position: relative;
    }
    .nav {
        position: absolute;
        display: block;
        background-color: blue;
        width: 100vw;
        height: 100vh;
        top: 0;
        left: 100vw;
        transition: all 0.3s linear;

        &.open {
            left: 0;
        }

        .nav-links{
            text-align: center;
        }

        @media (min-width: 768px) {
            left: 0;
            height: auto;
            .nav-links{
                text-align: right;
            }
            .nav-item, a {
                display: inline;
            }
        }
    }
</style>