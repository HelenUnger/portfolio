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
                <span class="dark-mode-btn" @click="toggleMode()">
                    NIGHT/DAY
                </span>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            openNav: false,
            darkMode: true
        };
    },

    methods: {
        toggleNav() {
            this.openNav = !this.openNav;
        },
        toggleMode() {
            this.darkMode = ! this.darkMode;
            this.$emit('dark-mode', this.darkMode);
        }
    }
}
</script>
<style lang="scss" scoped>
    .navigation-container {
        z-index: 1;
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
            .dark-mode-btn {
                display: none;
            }
        }

        @media (min-width: 768px) {
            left: 0;
            height: 50px;
            background-color: inherit;
            .nav-links{
                text-align: right;
                .nav-item, a, .dark-mode-btn {
                    display: inline;
                }
            }
        }
    }
</style>